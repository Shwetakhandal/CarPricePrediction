# CarPricePrediction



    Problem Statement
    
    You need to build a linear regression model to predict prices of cars based on its technical specifications such as car manufacturer, its engine capacity, fuel efficiency, body-type etc.
    
    Dataset Description:
    
    "The dataset contains 205 rows and 26 columns. Each column represents an attribute of a car as described in the table below."


    Attribute Information

     |1| Car_ID-Unique id of each car (Integer)

     |2| Symboling-Assigned insurance risk rating; a value of +3 indicates that the car is risky; -3 suggests that it is probably a safe car (Categorical)
     
     |3| carCompany- Name of car company (Categorical)
     
     |4|fueltype-  fuel-type i.e. petrol or diesel (Categorical)
     
     |5|aspiration|Aspiration used in a car (Categorical)
    
     |6|doornumber|Number of doors in a car (Categorical)|\t\t\n",
     
     |7|carbody|Body-type of a car (Categorical)|\n",
     
     |8|drivewheel|Type of drive wheel (Categorical)|\n",
     
     |9|enginelocation|Location of car engine (Categorical)|\n",
     
     |10|wheelbase|Weelbase of car (Numeric)|\t\t\n",
     
     |11|carlength|Length of car (Numeric)|\t\t\n",
     
     |12|carwidth|Width of car (Numeric)|\n",
     
     |13|carheight|Height of car (Numeric)|\n",
     
     |14|curbweight|The weight of a car without occupants or baggage (Numeric)|\n",
     
     |15|enginetype|Type of engine (Categorical)
     
     |16|cylindernumber|Number of cylinders placed in the car engine (Categorical)||17|enginesize|Capacity of an engine (Numeric)
     
     |18|fuelsystem|Fuel system of a car (Categorical)
     
     |19|boreratio|Bore ratio of car (Numeric)
     
     |20|stroke|Stroke or volume inside the engine (Numeric)
     
     |21|compressionratio|Compression ratio of an engine (Numeric)
     
     |22|horsepower|Power output of an engine (Numeric)
     
     |23|peakrpm|Peak revolutions per minute (Numeric)
     
     |24|citympg|Mileage in city (Numeric)
     
     |25|highwaympg|Mileage on highway (Numeric)
     
     |26|price(Dependent variable)|Price of a car (Numeric)

    "This data set consists of three types of entities
  
     the specification of an auto in terms of various characteristics
    
     its assigned insurance risk rating,
     
    "- its normalised losses in use as compared to other cars.
    
    "The second rating corresponds to the degree to which the auto is more risky than its price indicates. 
     Cars are initially assigned a risk factor symbol associated with its price. Then, if it is more risky (or less), 
     this symbol is adjusted by moving it up (or down) the scale. Actuarians call this process **symboling**. 
     A value of $+3$ indicates that the auto is risky, $-3$ that it is probably pretty safe.
    
    "The third factor is the relative average loss payment per insured vehicle year. This value is normalized for 
    all autos within a particular size classification (two-door small, station wagons, sports/speciality etc.),
    and represents the average loss per car per year.
  
