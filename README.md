# 340Final

# The FoodTruckDB code creates a database that hold information on food trucks. 

# It does this by creating 4 tables, Users, Map, Trucks, and Comments.

# Within the Users table it collects a username and password, then gives the user a role. 
# A user can either be an owner or a customer. The role will allow for certain people to added their food truck to the map.
# This is so a customer can't delete a truck off of the map or change any information about the truck

# Within the Map table it collect location information, the address, and then its corrdinates.
# This will allow for a dot to be added to a map of where this food truck was

# Within
CREATE TABLE Trucks (
      name VARCHAR(50) PRIMARY KEY,
      type VARCHAR(50),
      overall_rating INT,
      address VARCHAR(100),
      FOREIGN KEY (address) REFERENCES Map(address)
);
CREATE TABLE Comments (
      comment_id INT PRIMARY KEY AUTO_INCREMENT,
      username VARCHAR(50),
      comment VARCHAR(100),
      rating INT,
      timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
      name VARCHAR(50),
      FOREIGN KEY (username) REFERENCES Users(username),
      FOREIGN KEY (name) REFERENCES Trucks(name)
);
