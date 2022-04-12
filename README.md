# Filtering Stars
* *Got the final list of habitable planets.*
* *Learned about more factors that make a planet habitable.*

## Steps To Find suitable planets For Survival
  * *In the last class, we came up with two lists (goldilock_planets & speed_supporting_planets).*
  * *Merge the two lists together to get a final list of habitable planets! The habitable planets would be the one which lie on the Goldilock Zone and also have supported speed! **(Code is given below)**.* 
  * *These extreme temperatures are because of the planet’s distance from the sun. We know that the goldilock zone could be anywhere from 0.38 to 2AU and both Mercury
and Venus lie in the Goldilock zone, still they are so hot.*
  * *These planets are hot because goldilock zone can be different for different solar systems. It depends on how big and powerful the star is. For us, we are in the
beginning of our solar system’s Goldilock Zone*
  * *To find exact goldilock zones for different stars is a bit difficult and there’s no such formula as yet, but the solar system having 0.38AU as goldilock zone would be much smaller than our sun and the solar system having goldilock zone higher than 1.5AU (could also be greater than 2, up to 10) are the stars that are much more bigger and powerful than our sun.*
  * *We will be making a final dictionary that will contain all the planets with the list of features that it exhibits (gravity support,planet type, goldilock zone and speed support) **(Code is given below)**.*
 
## Code is given below
* **Code to merge the goldilock list and speed list**
````
habitable_planets = []
for planet in speed_supporting_planets:
if planet in goldilock_planets:
 habitable_planets.append(planet)
print(len(habitable_planets))
````
* **Code to make a final dictionary**
````
final_dict = {}
for index, planet_data in enumerate(planet_data_rows):
 features_list = []
 gravity = (float(planet_data[3])*5.972e+24) /
(float(planet_data[7])*float(planet_data[7])*6371000*6371000) *
6.674e-11
try:
 if gravity < 100:
 features_list.append("gravity")
except: pass
try:
 if planet_data[6].lower() == "terrestrial" or
planet_data[6].lower() == "super earth":
 features_list.append("planet_type")
except: pass
try:
 if planet_data[8] > 0.38 or planet_data[8] < 2:
 features_list.append("goldilock")
except: pass
try:
 distance = 2 * 3.14 * (planet_data[8] * 1.496e+9)
 time = planet_data[9] * 86400
 speed = distance / time
 if speed < 200:
 features_list.append("speed")
except: pass
 final_dict[index] = features_list
print(final_dict)
````

## Facts :
* *Now that we have the final list of habitable planets, are they really habitable? Some facts:
   * *In our solar system, we know that the first 4 planets (Mercury, Venus, Earth and Mars) are Terrestrial Planets.*
   * *Rest of the planets are either Gas Giants or Neptune Like.*
* *The first thing we filtered out is Gravity :*
   * *Mercury - 3.7m/s*
   * *Venus - 8.87m/s*
   * *Earth - 9.8m/s*
   * *Mars - 3.8m/s*
* *We know that all these planets are Terrestrial already. Now, check the distance of these planets from the Sun.*
   * *Mercury - 0.4AU*
   * *Venus - 0.7AU*
   * *Earth - 1AU*
   * *Mars - 1.5AU.*
* *This again, makes all the planets lie in the Goldilock Zone. If we talk about the speed of these planets:*
   * *Mercury - 47km/s*
   * *Venus - 35km/s*
   * *Earth - 30km/s*
   * *Mars - 24km/s*
* *All these planets have suitable speed. Despite all the planets being clearing our filters, we are still only considering the possibility of colonizing Mars! The reason why other planets are not suitable for colonizing them:*
   * *Mercury - Mercury is not habitable since it does not have an atmosphere and its temperature varies from 100 Degree Celsius to 700 Degree Celsius.*
   * *Venus - Venus is an extreme planet. It’s very hot. It’s atmosphere traps the heat on the surface and it’s temperature is a whooping 700 Degree Celsius.It also rains sulphuric acid.*
   * *Earth - Seems like just the right planet to exist.*
   * *Mars - Mars has some atmosphere and it also has some water on its surface. The temperatures are a bit extreme (20 Degree Celsius to -150 Degree Celsius) but it’s still manageable.*
* *Apart from this, the planets could also be tidally locked to their sun. This means that one side always faces the sun and the other side always faces away from the sun.Here on Earth, we have our days warmer as compared to nights.When planets are tidally locked, one side of the planet might be extremely hot and the other side might be extremely cold.For reference, our Moon is tidally locked to our planet Earth. We can always see only one side of the moon and the other side is never visible to us.*
