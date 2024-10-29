# Venkata@startuml
class User {
    - id : String
    - username : String
    - email : String
    + addresses : List<Address>
    + phoneNumbers : List<PhoneNumber>
    + organizations : List<Organization>
    + termsAndConditions : List<TermsAndConditions>
    + loginHistory : List<LoginHistory>
}

class Address {
    - street : String
    - city : String
    - state : String
    - zip : String
    - country : String
}

class PhoneNumber {
    - number : String
    - extension : String
    + tags : List<String>
}

class Organization {
    - id : String
    - name : String
}

class TermsAndConditions {
    - id : String
    - documentId : String
    - agreementAcceptedDateTime : LocalDateTime
    - userAgreement : String
}

class LoginHistory {
    - id : String
    - userId : String
    - loginDateTime : LocalDateTime
    - loginStatus : String
}

class UserService {
    + createUser(request: UserCreateRequest) : User
    + updateUser(request: UserUpdateRequest) : User
    + deleteUser(request: UserDeleteRequest) : boolean
    + retrieveUser(userId: String) : User
}

User "1" -- "*" Address
User "1" -- "*" PhoneNumber
User "1" -- "*" Organization
User "1" -- "*" TermsAndConditions
User "1" -- "*" LoginHistory
@enduml
