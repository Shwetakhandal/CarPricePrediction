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
    
    "The second rating corresponds to the degree to which the auto is more risky than its price indicates. Cars are initially assigned a risk factor symbol associated with its price. Then, if it is more risky (or less), this symbol is adjusted by moving it up (or down) the scale. Actuarians call this process **symboling**. A value of $+3$ indicates that the auto is risky, $-3$ that it is probably pretty safe.
    
    "The third factor is the relative average loss payment per insured vehicle year. This value is normalized for all autos within a particular size classification (two-door small, station wagons, sports/speciality etc.), and represents the average loss per car per year.
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>car_ID</th>\n",
       "      <th>symboling</th>\n",
       "      <th>CarName</th>\n",
       "      <th>fueltype</th>\n",
       "      <th>aspiration</th>\n",
       "      <th>doornumber</th>\n",
       "      <th>carbody</th>\n",
       "      <th>drivewheel</th>\n",
       "      <th>enginelocation</th>\n",
       "      <th>wheelbase</th>\n",
       "      <th>...</th>\n",
       "      <th>enginesize</th>\n",
       "      <th>fuelsystem</th>\n",
       "      <th>boreratio</th>\n",
       "      <th>stroke</th>\n",
       "      <th>compressionratio</th>\n",
       "      <th>horsepower</th>\n",
       "      <th>peakrpm</th>\n",
       "      <th>citympg</th>\n",
       "      <th>highwaympg</th>\n",
       "      <th>price</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>alfa-romero giulia</td>\n",
       "      <td>gas</td>\n",
       "      <td>std</td>\n",
       "      <td>two</td>\n",
       "      <td>convertible</td>\n",
       "      <td>rwd</td>\n",
       "      <td>front</td>\n",
       "      <td>88.6</td>\n",
       "      <td>...</td>\n",
       "      <td>130</td>\n",
       "      <td>mpfi</td>\n",
       "      <td>3.47</td>\n",
       "      <td>2.68</td>\n",
       "      <td>9.0</td>\n",
       "      <td>111</td>\n",
       "      <td>5000</td>\n",
       "      <td>21</td>\n",
       "      <td>27</td>\n",
       "      <td>13495.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>3</td>\n",
       "      <td>alfa-romero stelvio</td>\n",
       "      <td>gas</td>\n",
       "      <td>std</td>\n",
       "      <td>two</td>\n",
       "      <td>convertible</td>\n",
       "      <td>rwd</td>\n",
       "      <td>front</td>\n",
       "      <td>88.6</td>\n",
       "      <td>...</td>\n",
       "      <td>130</td>\n",
       "      <td>mpfi</td>\n",
       "      <td>3.47</td>\n",
       "      <td>2.68</td>\n",
       "      <td>9.0</td>\n",
       "      <td>111</td>\n",
       "      <td>5000</td>\n",
       "      <td>21</td>\n",
       "      <td>27</td>\n",
       "      <td>16500.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>alfa-romero Quadrifoglio</td>\n",
       "      <td>gas</td>\n",
       "      <td>std</td>\n",
       "      <td>two</td>\n",
       "      <td>hatchback</td>\n",
       "      <td>rwd</td>\n",
       "      <td>front</td>\n",
       "      <td>94.5</td>\n",
       "      <td>...</td>\n",
       "      <td>152</td>\n",
       "      <td>mpfi</td>\n",
       "      <td>2.68</td>\n",
       "      <td>3.47</td>\n",
       "      <td>9.0</td>\n",
       "      <td>154</td>\n",
       "      <td>5000</td>\n",
       "      <td>19</td>\n",
       "      <td>26</td>\n",
       "      <td>16500.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>2</td>\n",
       "      <td>audi 100 ls</td>\n",
       "      <td>gas</td>\n",
       "      <td>std</td>\n",
       "      <td>four</td>\n",
       "      <td>sedan</td>\n",
       "      <td>fwd</td>\n",
       "      <td>front</td>\n",
       "      <td>99.8</td>\n",
       "      <td>...</td>\n",
       "      <td>109</td>\n",
       "      <td>mpfi</td>\n",
       "      <td>3.19</td>\n",
       "      <td>3.40</td>\n",
       "      <td>10.0</td>\n",
       "      <td>102</td>\n",
       "      <td>5500</td>\n",
       "      <td>24</td>\n",
       "      <td>30</td>\n",
       "      <td>13950.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>2</td>\n",
       "      <td>audi 100ls</td>\n",
       "      <td>gas</td>\n",
       "      <td>std</td>\n",
       "      <td>four</td>\n",
       "      <td>sedan</td>\n",
       "      <td>4wd</td>\n",
       "      <td>front</td>\n",
       "      <td>99.4</td>\n",
       "      <td>...</td>\n",
       "      <td>136</td>\n",
       "      <td>mpfi</td>\n",
       "      <td>3.19</td>\n",
       "      <td>3.40</td>\n",
       "      <td>8.0</td>\n",
       "      <td>115</td>\n",
       "      <td>5500</td>\n",
       "      <td>18</td>\n",
       "      <td>22</td>\n",
       "      <td>17450.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 26 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "   car_ID  symboling                   CarName fueltype aspiration doornumber  \\\n",
       "0       1          3        alfa-romero giulia      gas        std        two   \n",
       "1       2          3       alfa-romero stelvio      gas        std        two   \n",
       "2       3          1  alfa-romero Quadrifoglio      gas        std        two   \n",
       "3       4          2               audi 100 ls      gas        std       four   \n",
       "4       5          2                audi 100ls      gas        std       four   \n",
       "\n",
       "       carbody drivewheel enginelocation  wheelbase  ...  enginesize  \\\n",
       "0  convertible        rwd          front       88.6  ...         130   \n",
       "1  convertible        rwd          front       88.6  ...         130   \n",
       "2    hatchback        rwd          front       94.5  ...         152   \n",
       "3        sedan        fwd          front       99.8  ...         109   \n",
       "4        sedan        4wd          front       99.4  ...         136   \n",
       "\n",
       "   fuelsystem  boreratio  stroke compressionratio horsepower  peakrpm citympg  \\\n",
       "0        mpfi       3.47    2.68              9.0        111     5000      21   \n",
       "1        mpfi       3.47    2.68              9.0        111     5000      21   \n",
       "2        mpfi       2.68    3.47              9.0        154     5000      19   \n",
       "3        mpfi       3.19    3.40             10.0        102     5500      24   \n",
       "4        mpfi       3.19    3.40              8.0        115     5500      18   \n",
       "\n",
       "   highwaympg    price  \n",
       "0          27  13495.0  \n",
       "1          27  16500.0  \n",
       "2          26  16500.0  \n",
       "3          30  13950.0  \n",
       "4          22  17450.0  \n",
       "\n",
       "[5 rows x 26 columns]"
      ]
     },
     "execution_count": 1,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
