Download Link: https://assignmentchef.com/product/solved-database-model-assignment-4-relational-algebra-operations
<br>
The following set of relations is from the East Coast Aquarium database that appears in Chapter 14 of your text book.  Read Chapter 14 to get a better understanding of these relations.

Species (Species Code, Latin Name, English Name)Location (Location Code, Place in Building, Size, Head Keeper)Population (Species Code, Location Code, Number of Animals)Food (Type of Food)Feeding (Species Code, Type of Food, Amount of Food, Feeding Interval)Habitats (Habitat Type)Can Live (Species Code, Habitat Type)Where Found (Location Code, Habitat Type)Source (Source Code, Source Name, Source Address, Source Phone, Contact Person)Can Supply (Source Code, Species Code)Shipment (P.O. #, Source Code, Order Date, Order Total $)Shipment Items (P.O. #, Species Code, Number of Animals, Each $, Line $)Give the relational algebra operations (i.e., RESTRICT, PROJECT, JOIN, UNION, DIFFERENCE/MINUS, PRODUCT, INTERSECT) for each query listed below.

For example, to answer the query “List the Order Date for the P.O. # 85093”, you would use the following two relational algebra operations:

RESTRICT FROM Shipment WHERE P.O. # = 85093 GIVING One OrderPROJECT Order Date FROM One Order GIVING One Order DateComplex examples:

1. List the names of all head keepers who are responsible for Hammerhead Sharks.

RESTRICT FROM Species WHERE English Name = ‘Hammerhead shark’ GIVING One Species

PROJECT Species Code FROM One Species GIVING One Species Code

JOIN One Species Code TO Population OVER Species Code GIVING One Species Locations

JOIN One Species Locations TO Location OVER Location Code GIVING Location Details

PROEJCT Head Keeper FROM Location Details GIVING Keeper Names(Note: Can drop first PROJECT above – just better perf this way – must join Species and Population instead of using One Species Code)

2. List the Latin name of all species that do not live in location 1 (the main tank).

RESTRICT FROM Population WHERE Location Code = 1 GIVING One Place

PROJECT Species Code FROM One Place GIVING Which Live There

PROJECT Species Code FROM Species GIVING Species List

Species List MINUS Which Live There GIVING Do Not Live There

JOIN Do Not Live There TO Species OVER Species Code GIVING All Data

PROJECT Latin Name FROM All Data GIVING Latin Name List

(Note: Be careful to handle species can habitat multiple tanks / locations)

Queries:

List the habitats that have species with code 155.

List the place in the building of all locations that are less than 50 gallons in size.List the types of food eaten by Bottlenose Dolphins.List the English name and species code of each species that live in location code 222.List the English name of all species that can live in a coral reef habitat.

List the Latin name of all species that eat meal worms.List the Latin name of all species that do not eat mealworms.List the contact person and phone number at each source that can supply harbor seals.

List the name of each source from which an animal costing more than $5,000 was ordered.

List the English name of all species that were ordered on purchase order # 85093.