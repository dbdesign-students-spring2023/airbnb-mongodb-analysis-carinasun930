### 1. Origin of the data
The data is from Airbnb database, and I  use the data form Barossa Valley, South Australia, Australia. You can find the data [here](http://insideairbnb.com/get-the-data/)

The original data file was in CSV. Here I show some parts of the original data. I didn't do the scrubbing because the data is in good shape, if I do scrubbing, it has the possibility that I would lose some useful information. Also, from the length of the file, this list contains managable number of houses, so I decide to keep them all.

| id      | listing_url                          | scrape_id | last_scraped | source          | name                                                |
|---------|--------------------------------------|-----------|--------------|-----------------|-----------------------------------------------------|
| 1125097 | https://www.airbnb.com/rooms/1125097 | 2.02E+13  | 3/29/2023    | city scrape     | Strathlyn Coach House Barossa                       |
| 1133195 | https://www.airbnb.com/rooms/1133195 | 2.02E+13  | 3/29/2023    | city scrape     | Strathlyn Lemon Tree Spa  Barossa                   |
| 1133236 | https://www.airbnb.com/rooms/1133236 | 2.02E+13  | 3/29/2023    | city scrape     | Strathlyn Spa Garden Suites Barossa                 |
| 1710462 | https://www.airbnb.com/rooms/1710462 | 2.02E+13  | 3/29/2023    | city scrape     | Shea-Oak Log Studio Shed                            |
| 1787389 | https://www.airbnb.com/rooms/1787389 | 2.02E+13  | 3/29/2023    | city scrape     | Barossa Valley Apt 1 offers 2 bedrooms 2 bathroom   |
| 2028951 | https://www.airbnb.com/rooms/2028951 | 2.02E+13  | 3/29/2023    | city scrape     | 2 bedrooms with Woodfire, Barossa Country Cottages  |
| 2327616 | https://www.airbnb.com/rooms/2327616 | 2.02E+13  | 3/29/2023    | city scrape     | Gawler River Farm B and B.                          |
| 2567051 | https://www.airbnb.com/rooms/2567051 | 2.02E+13  | 3/29/2023    | city scrape     | The Miners Cottage Barossa Valley                   |
| 5289072 | https://www.airbnb.com/rooms/5289072 | 2.02E+13  | 3/29/2023    | city scrape     | Mt McKenzie Raspberry Farm                          |
| 5426792 | https://www.airbnb.com/rooms/5426792 | 2.02E+13  | 3/29/2023    | city scrape     | "The Shed"                                          |
| 5537173 | https://www.airbnb.com/rooms/5537173 | 2.02E+13  | 3/29/2023    | city scrape     | 1837 Barossa Luxury  Vineyard   Cottage S Australia |
| 6149133 | https://www.airbnb.com/rooms/6149133 | 2.02E+13  | 3/29/2023    | city scrape     | The Reserve Barossa Valley                          |
| 6157653 | https://www.airbnb.com/rooms/6157653 | 2.02E+13  | 3/29/2023    | city scrape     | Barossa Barn Bed & Breakfast                        |
| 6170279 | https://www.airbnb.com/rooms/6170279 | 2.02E+13  | 3/29/2023    | previous scrape | Little Para Cottage                                 |
| 6170887 | https://www.airbnb.com/rooms/6170887 | 2.02E+13  | 3/29/2023    | city scrape     | Elderton Wines Guest House                          |
| 6296823 | https://www.airbnb.com/rooms/6296823 | 2.02E+13  | 3/29/2023    | city scrape     | Cosy 2-bedroom Cottage in the heart of the Barossa  |
| 7055506 | https://www.airbnb.com/rooms/7055506 | 2.02E+13  | 3/29/2023    | previous scrape | Vineyard Cottage - Under the Vines                  |
| 7297171 | https://www.airbnb.com/rooms/7297171 | 2.02E+13  | 3/29/2023    | city scrape     | Pembury Chase Barossa Valley                        |
| 8053447 | https://www.airbnb.com/rooms/8053447 | 2.02E+13  | 3/29/2023    | city scrape     | Angels Place: Private Suite                         |
| 9264671 | https://www.airbnb.com/rooms/9264671 | 2.02E+13  | 3/29/2023    | city scrape     | Barossa Idyll Studio -great for romantics           |

### 2. Analysis
#### 1. Show exactly two documents from the `listings` collection in any order
``` 
db.listings.find().limit(2);
```

##### Results:
```[
  {
    _id: ObjectId("6432142224ed4983868c0278"),
    id: 6149133,
    listing_url: 'https://www.airbnb.com/rooms/6149133',
    scrape_id: Long("20230329041125"),
    last_scraped: '2023-03-29',
    source: 'city scrape',
    name: 'The Reserve Barossa Valley',
    description: 'Set on 6 private acres of manicured gardens, our Seppeltsfield Road property has amazing views across Shiraz vines from the 6 person spa and plenty of room to roam in the orchid, wineries just over the road or create a feast in the wood fired oven.<br /><br /><b>The space</b><br />When you arrive, you will love, love, love the home... it is so relaxing and casual you will not want to leave<br /><br /><b>Guest access</b><br />We do have a refundable bond prior to access.  As you can appreciate you have the entire home to yourself, hence the bond.<br /><br /><b>Other things to note</b><br />The gardens do require attending to, depending on the season it can vary each week.',
    neighborhood_overview: 'Everything is very close, winery 50m across the road and 150m, amazing dining experiences 3 minutes by car.  You are surrounded in the best Shiraz vineyards in the world.  Tanunda and Nuriootpa are both 4minutes by car!',
    picture_url: 'https://a0.muscache.com/pictures/76641932/15301fab_original.jpg',
    host_id: 31898226,
    host_url: 'https://www.airbnb.com/users/show/31898226',
    host_name: 'Simone',
    host_since: '2015-04-25',
    host_location: 'South Australia, Australia',
    host_about: '',
    host_response_time: 'N/A',
    host_response_rate: 'N/A',
    host_acceptance_rate: '0%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/users/31898226/profile_pic/1429959930/original.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/users/31898226/profile_pic/1429959930/original.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 1,
    host_total_listings_count: 1,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 'f',
    neighbourhood: 'Nuriootpa, South Australia, Australia',
    neighbourhood_cleansed: 'Nuriootpa',
    neighbourhood_group_cleansed: '',
    latitude: -34.49133,
    longitude: 138.96615,
    property_type: 'Entire home',
    room_type: 'Entire home/apt',
    accommodates: 10,
    bathrooms: '',
    bathrooms_text: '3 baths',
    bedrooms: 5,
    beds: 5,
    amenities: '["Air conditioning", "Kitchen", "Indoor fireplace", "Free parking on premises", "Hot tub", "Heating", "Fire extinguisher", "Smoke alarm", "TV", "Washer", "Shampoo", "Wifi", "First aid kit", "Dryer", "Essentials"]',
    price: '$1,600.00',
    minimum_nights: 2,
    maximum_nights: 1125,
    minimum_minimum_nights: 2,
    maximum_minimum_nights: 2,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 2,
    maximum_nights_avg_ntm: 1125,
    calendar_updated: '',
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 16,
    calendar_last_scraped: '2023-03-29',
    number_of_reviews: 3,
    number_of_reviews_ltm: 1,
    number_of_reviews_l30d: 0,
    first_review: '2016-04-26',
    last_review: '2022-05-02',
    review_scores_rating: 5,
    review_scores_accuracy: 5,
    review_scores_cleanliness: 5,
    review_scores_checkin: 5,
    review_scores_communication: 5,
    review_scores_location: 5,
    review_scores_value: 4,
    license: '',
    instant_bookable: 'f',
    calculated_host_listings_count: 1,
    calculated_host_listings_count_entire_homes: 1,
    calculated_host_listings_count_private_rooms: 0,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 0.04
  },
  {
    _id: ObjectId("6432142224ed4983868c026d"),
    id: 1125097,
    listing_url: 'https://www.airbnb.com/rooms/1125097',
    scrape_id: Long("20230329041125"),
    last_scraped: '2023-03-29',
    source: 'city scrape',
    name: 'Strathlyn Coach House Barossa',
    description: 'Please note there is a minimum stay of 2 nights.<br />Make use of the new Gymnasium and Guest Laundry on the property.<br />Enjoy the location set among the vineyards.<br />Conveniently close to the town of Angaston, cafes, restaurants, wineries and  bike track.<br /><br /><b>The space</b><br />Strathlyn Coach House is an independent building located at Strathlyn Estate, a privately owned 5 acre historic property located on the fringe of Angaston in the Barossa Valley. The coach house was constructed circa 1905 was restored in 1995 as comfortable accommodation for two. Built of local stone with 30 centimetre walls, the coach house is quite an historic landmark, testifying to life of a bygone era.<br /><br />The outside of the building remains much the same as it was in 1905, but the interior has been finished with extensive use of timber. A mezzanine level bedroom has been created from the original loft floor.<br /><br />A large balcony area, reached from the attractive bedroom, has pa',
    neighborhood_overview: 'Strathlyn Estate is a very private property surrounded by extensive gardens. It is off the main road located amongst vineyards within walking distance of Saltram Winery. The accommodation is 1 km from Angaston town where guests can access the start of the bike track that runs through the centre of the Barossa Valley to Gawler.',
    picture_url: 'https://a0.muscache.com/pictures/16953708/b789c3ad_original.jpg',
    host_id: 6172214,
    host_url: 'https://www.airbnb.com/users/show/6172214',
    host_name: 'Heather',
    host_since: '2013-05-01',
    host_location: '',
    host_about: 'I have been a long time resident of the Barossa Valley.I would be happy to provide you with information about local points of interest.',
    host_response_time: 'within a few hours',
    host_response_rate: '100%',
    host_acceptance_rate: '92%',
    host_is_superhost: 't',
    host_thumbnail_url: 'https://a0.muscache.com/im/users/6172214/profile_pic/1367919828/original.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/users/6172214/profile_pic/1367919828/original.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 3,
    host_total_listings_count: 4,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood: 'Angaston, South Australia, Australia',
    neighbourhood_cleansed: 'Angaston',
    neighbourhood_group_cleansed: '',
    latitude: -34.49389,
    longitude: 139.02942,
    property_type: 'Entire cottage',
    room_type: 'Entire home/apt',
    accommodates: 2,
    bathrooms: '',
    bathrooms_text: '1 bath',
    bedrooms: 1,
    beds: 1,
    amenities: '["Air conditioning", "Breakfast", "Extra pillows and blankets", "Coffee maker", "Hot water", "Iron", "Hair dryer", "Backyard", "Smoke alarm", "Security cameras on property", "TV", "First aid kit", "Patio or balcony", "Dryer", "Essentials", "Kitchen", "Hangers", "Refrigerator", "Dishes and silverware", "Private entrance", "Shampoo", "Free parking on premises", "Stove", "Bed linens", "Host greets you", "Luggage dropoff allowed", "Heating", "Fire extinguisher", "Cooking basics", "BBQ grill", "Washer", "Gym"]',
    price: '$254.00',
    minimum_nights: 2,
    maximum_nights: 14,
    minimum_minimum_nights: 2,
    maximum_minimum_nights: 2,
    minimum_maximum_nights: 14,
    maximum_maximum_nights: 14,
    minimum_nights_avg_ntm: 2,
    maximum_nights_avg_ntm: 14,
    calendar_updated: '',
    has_availability: 't',
    availability_30: 16,
    availability_60: 43,
    availability_90: 73,
    availability_365: 346,
    calendar_last_scraped: '2023-03-29',
    number_of_reviews: 182,
    number_of_reviews_ltm: 32,
    number_of_reviews_l30d: 1,
    first_review: '2013-09-13',
    last_review: '2023-03-12',
    review_scores_rating: 4.87,
    review_scores_accuracy: 4.96,
    review_scores_cleanliness: 4.9,
    review_scores_checkin: 4.99,
    review_scores_communication: 4.98,
    review_scores_location: 4.97,
    review_scores_value: 4.73,
    license: '',
    instant_bookable: 'f',
    calculated_host_listings_count: 3,
    calculated_host_listings_count_entire_homes: 2,
    calculated_host_listings_count_private_rooms: 1,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 1.57
  }
]
```
##### Insight:
This shows the first two documents in the lists with all of their information displayed

#### 2.Show exactly 10 documents in any order, but "prettyprint" in easier to read format, using the `pretty()` function.
``` 
db.listings.find().limit(10).pretty()
``` 

##### I export two results here:
```
{
    _id: ObjectId("6432142224ed4983868c0273"),
    id: 2028951,
    listing_url: 'https://www.airbnb.com/rooms/2028951',
    scrape_id: Long("20230329041125"),
    last_scraped: '2023-03-29',
    source: 'city scrape',
    name: '2 bedrooms with Woodfire, Barossa Country Cottages',
    description: `Relax as a couple, or with the whole family, at our peaceful cottage. Historic Lyndoch is the ideal place from which to experience the famous Barossa Valley.  The cottage is just a short 800 metres from the shops, bakery, and more. Restaurants and vineyards are within minutes. We supply free bicycles to explore the Barossa Cycling trails (Pre booking required). A second cottage is available on the site if you search airbnb for " 2 bedroom family cottage - sleeps up to 6 "<br /><br /><b>The space</b><br />Each cottage has 2 full bedrooms, a full kitchen, 3 way bathroom, and separate lounge/dining area. There is a balcony with outdoor chairs at the front of each cottage, and an undercover barbeque area as well.  Free Wi-Fi is available. There is a washing machine in each cottage, and also a children's playgym. This cottage has one queen bed , and in the second bedroom a double bed.<br /><br />We supply a welcome basket which includes biscuits, tea, coffee pods, noodles, porridge, bottled`,
    neighborhood_overview: '',
    picture_url: 'https://a0.muscache.com/pictures/miso/Hosting-2028951/original/3bf45951-2894-4638-882c-a45cd1fd7068.jpeg',
    host_id: 10421165,
    host_url: 'https://www.airbnb.com/users/show/10421165',
    host_name: 'Mark And Fiona',
    host_since: '2013-12-04',
    host_location: 'Lyndoch, Australia',
    host_about: 'Hi, We love hosting people at our cottages in the Barossa, both at the 1890s historic Barossa Hills Cottages in Springton, and these two bedroom family cottages at Lyndoch. In February 2022 the previous owners retired, and we have now refreshed the cottages - which are renowned throughout the Barossa as affordable family (& pet!) friendly accommodation.',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '100%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/ac9ad189-b8a2-448d-a071-8e40760ddf46.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/ac9ad189-b8a2-448d-a071-8e40760ddf46.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 2,
    host_total_listings_count: 3,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 'f',
    neighbourhood: '',
    neighbourhood_cleansed: 'Lyndoch',
    neighbourhood_group_cleansed: '',
    latitude: -34.60374,
    longitude: 138.88348,
    property_type: 'Entire vacation home',
    room_type: 'Entire home/apt',
    accommodates: 4,
    bathrooms: '',
    bathrooms_text: '1 bath',
    bedrooms: 2,
    beds: 2,
    amenities: '["Air conditioning", "Dedicated workspace", "Coffee maker", "Pack \\u2019n play/Travel crib", "Iron", "Free washer \\u2013 In unit", "Hair dryer", "Indoor fireplace: wood-burning", "Outdoor dining area", "Pets allowed", "Smoke alarm", "32\\" HDTV", "First aid kit", "Kitchen", "Refrigerator", "Private patio or balcony", "Dishes and silverware", "Garden view", "Shared backyard \\u2013 Fully fenced", "Lockbox", "Free parking on premises", "Self check-in", "Crib", "Heating", "Fire extinguisher", "Cooking basics", "BBQ grill", "High chair", "Wifi"]',
    price: '$194.00',
    minimum_nights: 2,
    maximum_nights: 999,
    minimum_minimum_nights: 2,
    maximum_minimum_nights: 2,
    minimum_maximum_nights: 2,
    maximum_maximum_nights: 999,
    minimum_nights_avg_ntm: 2,
    maximum_nights_avg_ntm: 210.7,
    calendar_updated: '',
    has_availability: 't',
    availability_30: 9,
    availability_60: 32,
    availability_90: 56,
    availability_365: 307,
    calendar_last_scraped: '2023-03-29',
    number_of_reviews: 11,
    number_of_reviews_ltm: 11,
    number_of_reviews_l30d: 1,
    first_review: '2022-04-10',
    last_review: '2023-02-27',
    review_scores_rating: 4.73,
    review_scores_accuracy: 4.91,
    review_scores_cleanliness: 4.91,
    review_scores_checkin: 4.91,
    review_scores_communication: 4.91,
    review_scores_location: 4.73,
    review_scores_value: 4.73,
    license: '',
    instant_bookable: 't',
    calculated_host_listings_count: 2,
    calculated_host_listings_count_entire_homes: 2,
    calculated_host_listings_count_private_rooms: 0,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 0.93
  },
  {
    _id: ObjectId("6432142224ed4983868c0274"),
    id: 2567051,
    listing_url: 'https://www.airbnb.com/rooms/2567051',
    scrape_id: Long("20230329041125"),
    last_scraped: '2023-03-29',
    source: 'city scrape',
    name: 'The Miners Cottage Barossa Valley',
    description: 'The Miners Cottage is beautifully restored with modern comforts and old world charm. Open fire, gorgeous bathroom, comfy bed, peace and quiet, sleeps two. The Miners Barn, right next to the cottage, can be added to your booking to sleep an extra two people. Beautiful views from every aspect. <br />A booking for four will be in two seperate cottages- two in the Miners Cottage and two in the Barn. They are right next to each other.<br /><br /><b>The space</b><br />The Miners Cottage - sleeps 2. Beautiful stone cottage with one bedroom, open fireplace, sitting room and kitchenette. Modern bathroom with claw foot bath, double shower, underfloor heating and heated towel rail.  Deep back veranda overlooks the pool and winter creek. Lovely red gum outdoor table for eating meals. BBQ & outdoor heater. Also have access to the full kitchen and TV sitting room in the Barn<br /><br /><br />The Miners Cottage Barn - sleeps 2. Old timber on the outside, modern on the inside. One bedroom with ensuite',
    neighborhood_overview: 'Set in rural surrounds on the edge of the Barossa, 7 mins to Lyndoch, 10 mins to Gawler, 15 mins to Tanunda, 30 mins to Angaston. <br /><br />Tour the wineries, visit the farmers market, eat out, ride the Bike trail, fossick in an antique store...',
    picture_url: 'https://a0.muscache.com/pictures/33850379/5f30c377_original.jpg',
    host_id: 10726293,
    host_url: 'https://www.airbnb.com/users/show/10726293',
    host_name: 'Rebecca',
    host_since: '2013-12-20',
    host_location: 'Cockatoo Valley, Australia',
    host_about: "Rebecca lives on the property with her husband and their 3 children.  They have a dog, cat, chooks, a duck and a few pet sheep.  Chances are you'll enjoy eggs fresh from the henhouse when you stay at The Miners Cottage!  ",
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '71%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/845c76d9-fe66-45b1-8424-ec5abfd5cd3a.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/845c76d9-fe66-45b1-8424-ec5abfd5cd3a.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 1,
    host_total_listings_count: 1,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 'f',
    neighbourhood: 'Cockatoo Valley, South Australia, Australia',
    neighbourhood_cleansed: 'Cockatoo Valley',
    neighbourhood_group_cleansed: '',
    latitude: -34.63884,
    longitude: 138.84564,
    property_type: 'Private room in bed and breakfast',
    room_type: 'Private room',
    accommodates: 4,
    bathrooms: '',
    bathrooms_text: '2 baths',
    bedrooms: 2,
    beds: 2,
    amenities: '["Air conditioning", "Breakfast", "Hot water", "Outdoor furniture", "Pack \\u2019n play/Travel crib", "Iron", "Hair dryer", "Pets allowed", "Smoke alarm", "TV", "First aid kit", "Dryer", "Essentials", "Kitchen", "Hangers", "Indoor fireplace", "Shampoo", "Free parking on premises", "Long term stays allowed", "Host greets you", "Heating", "Fire extinguisher", "BBQ grill", "Washer", "High chair", "Outdoor dining area", "Private pool"]',
    price: '$210.00',
    minimum_nights: 2,
    maximum_nights: 1125,
    minimum_minimum_nights: 2,
    maximum_minimum_nights: 2,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 2,
    maximum_nights_avg_ntm: 1125,
    calendar_updated: '',
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 11,
    availability_365: 232,
    calendar_last_scraped: '2023-03-29',
    number_of_reviews: 31,
    number_of_reviews_ltm: 4,
    number_of_reviews_l30d: 0,
    first_review: '2014-11-10',
    last_review: '2022-08-22',
    review_scores_rating: 4.84,
    review_scores_accuracy: 4.87,
    review_scores_cleanliness: 4.9,
    review_scores_checkin: 5,
    review_scores_communication: 4.94,
    review_scores_location: 4.84,
    review_scores_value: 4.74,
    license: '',
    instant_bookable: 'f',
    calculated_host_listings_count: 1,
    calculated_host_listings_count_entire_homes: 0,
    calculated_host_listings_count_private_rooms: 1,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 0.3
  },
 ]

```
##### Insight:
This shows the first two documents in the list, but in a prettier and readable format.

#### 3. Choose two hosts (by reffering to their `host_id` values) who are superhosts (available in the `host_is_superhost` field), and show all of the listings offered by both of the two hosts
    -   only show the `name`, `price`, `neighbourhood`, `host_name`, and `host_is_superhost` for each result
``` 
db.listings.find( { $or: [ {id: 1125097 }, { id: 1133195 }] }, {name:1,price:1,neighbourhood:1,host_name:1,host_is_superhost:1})
```

#####  The results are below: I chose id number 1125097 and also 1133195.
``` 
[
  {
    _id: ObjectId("6432142224ed4983868c026d"),
    name: 'Strathlyn Coach House Barossa',
    host_name: 'Heather',
    host_is_superhost: 't',
    neighbourhood: 'Angaston, South Australia, Australia',
    price: '$254.00'
  },
  {
    _id: ObjectId("6432142224ed4983868c026e"),
    name: 'Strathlyn Lemon Tree Spa  Barossa',
    host_name: 'Heather',
    host_is_superhost: 't',
    neighbourhood: 'Angaston, South Australia, Australia',
    price: '$236.00'
  }
]
```
##### Insights:
I picked two random super hosts and showed the required information. These information are the main information of the house, and can be used as filters when consumers searching for their ideal houses.

#### 4. Find all the unique `host_name` values 
``` 
db.listings.distinct("host_name")
``` 

##### Here are the results for part of the hosts
``` 
[
  'Adele',           'Alex',            'Alexandra',
  'Alicia',          'Andrew',          'Andrew & Belinda',
  'Angela',          'Ankica',          'Anna And David',
  'Anne',            'Anne-Marie',      'Annika',
  'Anthea',          'Awesome',         'Ben',
  'Bianca',          'Bill',            'Brett',
  'Bridget',         'Brooke & Peter',  'Cabn',
  'Carl',            'Carolyn',         'Cathy',
  'Charlotte',       'Charmaine',       'Chelsea',
  'Christina',       'Cory',            'Danielle',
  'Darren',          'David And Ruth',  'Deb',
  'Dianne',          'Dorham',          'Elderton',
  'Emma',            'Emma&Roger',      'Erika',
  'Evelyn',          'Filomena',        'Francis',
  'Georgie',         'Georgina',        'Gingerbread-Haus',
  'Graeme & Fleur',  'Grant And Cathy', 'Greenock Estate Wines',
  'Greg And Mary',   'Hannah',          'Heather',
  'Henri',           'Hewitson Winery', 'Hui',
  'Intrepid BnB',    'Jacqueline',      'James',
  'Jan',             'Jane',            'Janine',
  'Jasmine',         'Jason',           'Jean-Claude',
  'Jerry',           'Jessica',         'Jo',
  'Jodie',           'John',            'John & Jess',
  'John And Bianca', 'Jon',             'Jonathan And Kate',
  'Josh',            'Josh And Jen',    'Josie & Andrew',
  'Julie',           'Julieanne',       'Karen',
  'Karina',          'Karl',            'Kate',
  'Katelin',         'Kay',             'Kerry',
  'Kirsten',         'Kylie',           'Kylie And Tom',
  'Kym',             'Leonie',          'Lesley Ann',
  'Linda',           'Lisa',            'Louise',
  'Lucia',           'Lydia',           'Mai',
  'Maple',           'Maria',           'Marilyn And Adam',
  'Mark',
  ... 73 more items
]
```
##### Insights:
This chart shows all the people that are hosts in this city. This question can be used for question like, "How many people in this city are hosts" or "What the names of all the hosts".

#### 5. Find all of the places that have more than 2 beds in a neighborhood of your choice (referred to as either the neighborhood or neighbourhood_group_cleansed fields in the data file), ordered by review_scores_rating descending, -   only show the `name`, `beds`, `review_scores_rating`, and `price`.
```
db.listings.find( { beds: { $gt: 2 }, neighbourhood_cleansed: "Kapunda",review_scores_rating:{ $ne:"" }}, { name: 1, beds: 1, review_scores_rating: 1, price: 1 }).sort({review_scores_rating:-1});
``` 

##### Results:
```[
  {
    _id: ObjectId("6432142224ed4983868c033c"),
    name: 'Anlaby Station - Manor House Three Bedrooms',
    beds: 3,
    price: '$372.00',
    review_scores_rating: 5
  },
  {
    _id: ObjectId("6432142224ed4983868c033e"),
    name: 'Anlaby Station - Head Gardeners Cottage 3 Bedroom',
    beds: 3,
    price: '$402.00',
    review_scores_rating: 5
  },
  {
    _id: ObjectId("6432142224ed4983868c0344"),
    name: 'Kiron - Cottage in Kapunda, gateway to the Barossa',
    beds: 3,
    price: '$160.00',
    review_scores_rating: 4.9
  },
  {
    _id: ObjectId("6432142224ed4983868c0326"),
    name: 'The Station - luxury group accommodation',
    beds: 9,
    price: '$1,800.00',
    review_scores_rating: 4.89
  },
  {
    _id: ObjectId("6432142224ed4983868c0339"),
    name: 'The olde Hamilton shop, Between Clare and Barossa',
    beds: 3,
    price: '$173.00',
    review_scores_rating: 4.89
  },
  {
    _id: ObjectId("6432142224ed4983868c0294"),
    name: 'A Barn in the Barossa',
    beds: 4,
    price: '$265.00',
    review_scores_rating: 4.77
  },
  {
    _id: ObjectId("6432142224ed4983868c0290"),
    name: 'Barossa Millhouse',
    beds: 4,
    price: '$239.00',
    review_scores_rating: 4.58
  }
]
```
##### Insights:
This can be the real data when consumers searching for houses in Kapunda with more than two beds, and also they filter the results by descending ratings.

#### 6.  Show the number of listings per host
```
db.listings.aggregate([{ $group:{_id:"$host_id",count:{$sum:1}}}]);
``` 

##### Part of the results:
```
[
  { _id: 469195852, count: 1 },
  { _id: 505423341, count: 1 },
  { _id: 156498827, count: 1 },
  { _id: 284867983, count: 1 },
  { _id: 274161665, count: 1 },
  { _id: 154813436, count: 1 },
  { _id: 265939095, count: 1 },
  { _id: 99672311, count: 1 },
  { _id: 491342431, count: 1 },
  { _id: 261496601, count: 1 },
  { _id: 255507745, count: 2 },
  { _id: 26147078, count: 6 },
  { _id: 410966448, count: 1 },
  { _id: 398692841, count: 1 },
  { _id: 239660458, count: 1 },
  { _id: 10421165, count: 2 },
  { _id: 474741294, count: 1 },
  { _id: 417586028, count: 1 },
  { _id: 93219392, count: 2 },
  { _id: 246654848, count: 2 }
]
```
##### Insights:
This chart is the direct display of the relationship between hosts and houses. We can see some have multiple houses in Airbnb (the one with 6 may be a housekeeper) but most of them just lent out their vacant houses so they may have 1 or 2 on Airbnb. 

#### 7. Find the average `review_scores_rating` per neighborhood, and only show the ones above a `95`, sorted in descending order of rating

```
db.listings.aggregate([{$group:{_id:"$neighbourhood_cleansed",average_rating:{$avg:"$review_scores_rating"}}},{$match:{average_rating:{$gt:4.75}}},{$sort:{average_rating:-1}}])
``` 

##### Results: 
```[
  { _id: 'Mount Pleasant', average_rating: 4.9875 },
  { _id: 'Williamstown', average_rating: 4.951428571428571 },
  { _id: 'Sandy Creek', average_rating: 4.945 },
  { _id: 'Kapunda', average_rating: 4.932941176470588 },
  { _id: 'Lyndoch', average_rating: 4.931904761904763 },
  { _id: 'Moculta', average_rating: 4.9275 },
  { _id: 'Springton', average_rating: 4.92375 },
  { _id: 'Greenock', average_rating: 4.904999999999999 },
  { _id: 'Flaxman Valley', average_rating: 4.903333333333333 },
  { _id: 'Eden Valley', average_rating: 4.8999999999999995 },
  { _id: 'Light Pass', average_rating: 4.898000000000001 },
  { _id: 'Altona', average_rating: 4.89 },
  { _id: 'Penrice', average_rating: 4.89 },
  { _id: 'Nuriootpa', average_rating: 4.881666666666667 },
  { _id: 'Buchfelde', average_rating: 4.87 },
  { _id: 'Gawler River', average_rating: 4.87 },
  { _id: 'Cockatoo Valley', average_rating: 4.87 },
  { _id: 'Mount Crawford', average_rating: 4.86625 },
  { _id: 'Concordia', average_rating: 4.85 },
  { _id: 'Angaston', average_rating: 4.85 }
]
Type "it" for more
```
##### Insights:
95% out of 5 is 4.75, and we can see there are many neighborhoods have a very high rating, indicating the tourism in this city is developing in good direction.

## Extra-credit
This assignment deserves extra credit because I used Python to connect Mongodb and get the same result regarding the same question. After typing the code provided in the instruction, I have the code for the question: 
-   find all of the places that have more than 2 `beds` in a neighborhood of your choosing, ordered by `review_scores_rating` descending
-   only show the `name`, `beds`, `review_scores_rating`, and `price`
``` 
for result in collection.find ({"neighbourhood_cleansed":"Kapunda","beds":{"$gt":2},"review_scores_rating":{"$ne":''}},{"name":1,"beds":1, "review_scores_rating":1,"price":1}).sort("review_scores_rating",pymongo.DESCENDING):
     print(result)
```

##### Then I got:

``` 
{'_id': ObjectId('6432142224ed4983868c033c'), 'name': 'Anlaby Station - Manor House Three Bedrooms', 'beds': 3, 'price': '$372.00', 'review_scores_rating': 5.0}
{'_id': ObjectId('6432142224ed4983868c033e'), 'name': 'Anlaby Station - Head Gardeners Cottage 3 Bedroom', 'beds': 3, 'price': '$402.00', 'review_scores_rating': 5.0}
{'_id': ObjectId('6432142224ed4983868c0344'), 'name': 'Kiron - Cottage in Kapunda, gateway to the Barossa', 'beds': 3, 'price': '$160.00', 'review_scores_rating': 4.9}
{'_id': ObjectId('6432142224ed4983868c0326'), 'name': 'The Station - luxury group accommodation', 'beds': 9, 'price': '$1,800.00', 'review_scores_rating': 4.89}
{'_id': ObjectId('6432142224ed4983868c0339'), 'name': 'The olde Hamilton shop, Between Clare and Barossa', 'beds': 3, 'price': '$173.00', 'review_scores_rating': 4.89}
{'_id': ObjectId('6432142224ed4983868c0294'), 'name': 'A Barn in the Barossa', 'beds': 4, 'price': '$265.00', 'review_scores_rating': 4.77}
{'_id': ObjectId('6432142224ed4983868c0290'), 'name': 'Barossa Millhouse', 'beds': 4, 'price': '$239.00', 'review_scores_rating': 4.58}
```

##### This is exactly the same result that I got before without Python. Whatever language I am using, as long as it works, it would be fine :)
