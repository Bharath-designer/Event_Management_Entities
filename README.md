# Event Management App

##Entities

**User**

UserId (PK)
HashedPassword
PasswordHashKey
Role (Client, Admin)
CreatedDate

**ClientProfile**

ClientProfileId (PK)
UserId (FK)
Email
FullName
PhoneNumber

**Event**

EventId (PK)
EventName
Description
CreatedDate

**QuotationRequest**

QuotationRequestId (PK)
UserId (FK)
EventId (FK)
ExpectedPeopleCount
EventLocation (OwnVenue, PrivateVenue)
EventDate
EventType
FoodPreference
AdditionalRequirements
Status (Pending, Accepted, Rejected) (By Admin)
RequestedDate

**QuotationResponse**

QuotationResponseId (PK)
QuotationRequestId (FK)
QuotedAmount (By the admin)
ResponseMessage
Status (Pending, Accepted, Rejected) (By Client)
ResponseDate

**EventDetails** (If the QuotationRequest is accepted by both)

EventDetailsId (PK)
QuotationRequestId (FK)
QuotationResponseId (FK)
EventSchedule (DateTime)
VenueDetails
CateringDetails
EntertainmentDetails
SpecialInstructions

**Payment**

PaymentId (PK)
QuotationResponsetId (FK)
Amount
PaymentDate
PaymentStatus (Pending, Completed, Failed)
PaymentMethod (CreditCard, PayPal, etc.)


**Notification**

NotificationId (PK)
UserId (FK)
Message
NotificationDate
IsRead

**Review**

ReviewId (PK)
QuotationResponseId (FK)
EventId (FK)
UserId (FK)
Rating
Comments
ReviewDate
