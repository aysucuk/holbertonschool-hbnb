### HBnB Evolution: Part 1 (Model + API)

Welcome to the beginning of our exciting journey in creating our own web application, HBnB Evolution, inspired by AirBnB using Python and Flask!

#### What's In Store for Part 1?

##### Designing with UML
We'll start by sketching the backbone of our application using UML (Unified Modeling Language), akin to creating the architectural blueprint for a building. This stage is crucial for determining how our classes and components will interact.

##### Testing Our Logic
Next, we will ensure everything functions as intended by creating tests for the API and business logic. Think of this as ensuring all the gears in a machine work seamlessly.

##### Implementing the API
This is where our blueprint comes to life. We'll use Flask to create an API that integrates with our business logic and file-based persistence system (for now).

##### File-Based Data Storage
Initially, we will use a simple file-based system for data storage, choosing a format like "text, JSON, XML," etc. Keep in mind that we'll transition to a database later, so build it smartly!

##### Packaging with Docker
Lastly, we'll wrap everything up in a Docker image, akin to packing your app in a container for easy deployment anywhere.

### The Three Layers of Our API:

1. **Services Layer:** This layer handles all requests and responses.
2. **Business Logic Layer:** The brain of the operation where all processing and decision-making happens.
3. **Persistence Layer:** Currently, our humble file system, but we'll move to a database later.

### The Data Model: Key Entities

- **Places:** The core of our app, each place (house, apartment, room) has attributes like name, description, address, city, latitude, longitude, host, rooms, bathrooms, price per night, max guests, amenities, and reviews.
- **Users:** Users can be owners (hosts) or reviewers (commenters). Attributes include email, password, first name, and last name. A user can host multiple places and review places they don't own.
- **Reviews:** User feedback and ratings for places.
- **Amenities:** Features like Wi-Fi, pools, etc., chosen from a catalog or added by users.
- **Country and City:** Places are tied to a city, and cities belong to a country, aiding in categorizing and searching places.

### Business Logic: Rules to Follow

- **Unique Users:** Identified by their email.
- **One Host per Place:** Each place must have exactly one host.
- **Flexible Hosting:** A user can host multiple places or none.
- **Open Reviewing:** Users can review places they don't own.
- **Amenity Options:** Places can have multiple amenities, and users can add new ones.
- **City-Country Structure:** Places belong to cities, cities belong to countries, and a country can have multiple cities.

As you design and implement these features, remember that our application will grow. Choices made now should allow for easy additions and changes later, especially when we switch from file-based to database storage.

### Standard Attributes for Entities

Every entity (except Country) must include:

- **Unique ID (UUID4):** Each object must have a globally unique identifier, generated using UUID4.
- **Creation Date (created_at):** Records the date and time when an object is created.
- **Update Date (updated_at):** Records the last update made to the object.

### Why These Attributes Matter

- **Uniqueness:** UUID4 ensures each entity is distinct, crucial for scalability.
- **Traceability:** Created_at and updated_at help track the lifecycle of each entity, aiding in debugging, auditing, and understanding user interactions over time.

### Implementation Tips

- **UUID4 Generation:** Use Python's `uuid` module to generate UUID4 IDs.
- **Timestamps:** Use Python's `datetime` module to record creation and update timestamps.

#### Authors
- Nigar Abdullayeva @NigarAbdullayeva1
- Aysu SadÄqova @aysucuk
