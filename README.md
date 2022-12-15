# Formula-One-natural-phenomena-analysis
Data Analysis of a Kaggle Formula One Dataset from 2013 to 2017 using Python PANDAS to compare the how the performance of a car is affected when the surroundings change.  
Dataset used :
Formula One Race Dataset from 1950 to 2017 from Kaggle.
Description :
Formula One is the pinnacle of Open wheeled Motorsport racing. Being a big fan of the sport,
I chose the Formula One dataset of all the races and the results from 2013 to 2017. I wanted
to analyze the most recent data available and compare the performances of the teams during
that period.
Races and results depend not only on the ability and talent of the driver and the caliber of the
car built by the constructor team but also depend on some natural phenomena such as the
altitude and the climate of where the race takes place.
For ‘Project 2’, I chose to analyze how natural phenomena can affect the outcomes of a
Formula One race.
Modules used :
PANDAS
The four datasets used to analyze race performance:
circuits.csv - contains data for all the venues and circuits where Formula One races take place
constructors.csv - contains information about all the Car constructors that take part in a race.
constructorResults.csv - contains the data of all the results, every race for each constructor.
races.csv - contains the data for every Grand Prix that took place between 2013 - 2018
Loading the data sets:
df1 = pd.read_csv('constructorResults.csv')
df2 = pd.read_csv('races.csv')
df3 = pd.read_csv('circuits.csv')
df4 = pd.read_csv('constructors.csv')
I used the df.merge() function to merge the datasets based on common columns and created a
central dataset with the required data points.
As these datasets contained data from 1950 to 2017, I reduced the size of the dataset to hold
values from 2013 to 2017. Columns containing unwanted values are dropped using the
df.drop() function.
dfmain - 23874 data points.
The df.groupby().agg.reset_index() function is used to create a data frame showcasing the
total points collected by each team from 2013 to 2017.
The data clearly shows that ‘Mercedes’ have been the dominant team over the five years
followed closely by ‘Red Bull’ and ‘Ferrari’.
dfwin = dfmain[dfmain.points >= 1]
dfwin
dfwin is the data frame containing data of those cars that finished the race and scored points.
FACET 1: ALTITUDE
F1 race analysts and engineers have found out that circuits at an altitude of 500 meters and
above affect the performance of the car drastically.
The data frame dfmain has thus been put into two separate data frames:
dfhighalt - containing the data of races held at an altitude of 500 meters and above
dflowalt - containing the data of races held at an altitude less than 500 meters.
- HIGH ALTITUDES:
This tells us that Mercedes and Red Bull were the most consistent teams in high-altitude
races, and had cars that were reliable in those conditions.
Again it is seen that Mercedes tops the leaderboard for high-altitude races with the best car of
the lot, but there is a shift in the standings of Red Bull and Ferrari, which tells us that
although the Ferrari wasn’t as reliable as the Red Bull, it performed better in terms of speed
and was the faster car in higher altitudes. Lotus, which was at a higher position overall too
slips down showing how poorly it performed at high altitudes.
- LOW ALTITUDES:
Amazingly, at low altitudes, the Williams was the most reliable car and was able to finish
races better than all others.
Although the Williams was the most reliable car, it was Mercedes again who had the fastest
car. Here again, there is a shift in the positions of Red Bull and Ferrari, portraying the
strength of Red Bull over Ferrari in low-altitude races. Lotus too seems to do much better
than its competitors at low-altitude races.
FACET 2: TEMPERATURE AND CLIMATE
The temperature and climate of a venue also affect the performance of cars and their engines.
The race circuits have been classified into ‘warm’ and ‘cold’ lists concerning the temperature
and climate of the venues.
- WARM CLIMATES:
Dataframe - dfwarmclimate
dfwarmclimate = dfwin[dfwin.name_x.isin(warm)]
Mercedes continue their tale of dominance, being the most reliable car in warm conditions.
Their engine seems to suit all conditions well and rarely is affected due to natural
phenomena.
We now take a look at the total points accumulated for each team.
Surprisingly, ‘Force India’ F1 team performs well in warmer climates while McLaren
perishes, losing out to Lotus. Lotus, who performed poorly in high altitudes, accordingly does
well in warmer climates.
- COLDER CLIMATES:
Dataframe - dfcoldclimate
dfcoldclimate = dfwin[dfwin.name_x.isin(cold)]
Ferrari finally with a dominant car that is reliable in colder conditions. Enough praise cannot
be given to Mercedes who have been the best constructor for all conditions possible.
The points table shows a different story,
‘Red Bull’ pip Ferrari, showing that having the most reliable car doesn’t always mean that
your car is faster than the others. As predicted, Lotus too fails in colder climates (higher
altitudes) and so does Sauber. Sauber, which was the best of the back-end cars, perform
miserably in colder climates.
CONCLUSION
To conclude, our hypothesis that car performance is affected by natural phenomena holds.
Though some teams may fly above this claim, most are privy to the controlling nature has
over them.
The world of Formula One is bound by the restrictions of money, and thus having a perfect
car is a utopian dream, but teams like Mercedes have shown that this dream can become a
possibility. They continued their era of dominance till the 2021 season. For the first time in 8
years, they have been overthrown by another team, which unsurprisingly is ‘Red Bull’. Red
Bull showed glimpses of their potential, sometimes when their car wasn’t reliable, they were
able to showcase their strength with speed and consistency.
In the future, I aim to take on a similar project which looks over how allocating more budget
to facets like aerodynamics and engine building helped F1 teams better than investing in
other areas.
