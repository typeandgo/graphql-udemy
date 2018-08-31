query GET_SPECIFIED_USER{
  user(id: "40") {
    id
    firstName
    age
  }
}

query GET_SPECIFIED_USER_WITH_COMPANY{
  user(id: "40") {
    id
    firstName
    age,
    company {
      name
    }
  }
}

query GET_SPECIFIED_COMPANY{
  company(id: "M3leA35") {
    id
    name
    description
  }
}

query GET_SPECIFIED_COMPANY_WITH_USERS{
  company(id: "2") {
    id
    name
    description
    users {
      id
      firstName
      age
      company {
        name
      }
    }
  }
}

query GET_LOTS_OF_COMPANY{
  company1: company(id: "1") {
    ...companyDetails
  },
  company2: company(id: "2") {
    ...companyDetails
  }
}

fragment companyDetails on Company {
  id
  name
  description
}

mutation ADD_NEW_USER {
  addUser(firstName: "Stephen", age: 26) {
    id
    firstName
    age
  }
}

mutation DELETE_EXISTING_USER {
  deleteUser(id: "p~e37JZ") {
    id
    firstName
    age
  }
}

mutation EDIT_EXISTING_USER {
  editUser(id: "40", firstName: "Dolores", age: 30, companyId: "2") {
    id
    firstName
    age
    company {
      id
      name
    }
  }
}

mutation ADD_NEW_COMPANY {
  addCompany( name: "Amazon", description: "shopping") {
    id
    name
    description
  }
}

mutation DELETE_EXISTING_COMPANY {
  deleteCompany(id: "M3leA35") {
    name
    description
  }
}

mutation EDIT_EXISTING_COMPANY {
  editCompany(id: "97oSaDp", name: "Microsoft", description: "software") {
    id
    name
    description
  }
}
