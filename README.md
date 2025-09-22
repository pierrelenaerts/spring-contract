# spring-contract

This repository contains Spring Cloud Contract definitions for the Contact API that can be used with WireMock Stub Runner.

## API Endpoints

### GET /api/contact

Returns contact information with random first and last names for any ID parameter.

**Request:**
```
GET /api/contact?id={any_value}
```

**Response:**
```json
{
    "id": "{id_from_request}",
    "firstName": "{random_first_name}",
    "lastName": "{random_last_name}",
    "email": "{firstName}.{lastName}@example.com"
}
```

The API accepts any ID value and returns random data from predefined first and last name lists:

**First Names:** Alice, Bob, Charlie, Diana, Emma, Frank, Grace, Henry, Ivy, Jack, Kate, Liam, Mia, Noah, Olivia

**Last Names:** Smith, Johnson, Williams, Brown, Jones, Garcia, Miller, Davis, Rodriguez, Martinez, Lopez, Taylor, Anderson, Thomas, Jackson

## Usage with Stub Runner

To use these stubs with Spring Cloud Contract Stub Runner:

1. Build the project: `mvn clean package`
2. The generated stubs JAR will be available in `target/spring-contracts-0.0.1-SNAPSHOT-stubs.jar`
3. Configure Stub Runner to use these stubs

## Features

- Accepts any ID parameter value
- Returns random combinations of first name and last name
- Uses WireMock response templates for dynamic content generation
- Compatible with Spring Cloud Contract Stub Runner