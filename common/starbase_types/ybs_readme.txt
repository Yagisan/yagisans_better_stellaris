#root = starbase
#from = player
# Weights in the ai_design part are multiplied with the base weight of 00_starbase_buildings.txt and 00_starbase_modules.txt
# Then, a random number between that value and and extra 50% of that it is ADDED to it
# F.e. 100 base weight multiplies with 2.00 = 200. Then we take a random number between 0 and 100 (50% of 200) and ADD it to 200. 235 then, for example
# This is done for ALL starbase modules and buildings in the list every time an evaluation is made
# And the building or module with the highest value will be chosen to being built
# The implication of that is that you can not balance the weights TOO FAR from each other - otherwise some modules will never be chosen, unless they are the only thing on the evaluation
# Due to the progression of the game and the unlocking of tech, though, it is often the case that there will only be 1 item on the list at any given time anyway
# How the AI/game selects which type to use:
# First of all, it will try to find one which fulfils both the potential trigger and has a positive weight_modifier
# If this succeeds, the starbase already has a type.
# If it fails, it will go through each starbase type that fulfils the potential trigger. Then it will check the ratio it has built (total of this type / total upgraded starbases) compared to the desired ratio. If it is set to desire a minimum value and owns less than that, it multiplies its ratio desire by * 100. Then it build according to that type's template.

# Each starbase and orbital type has been separated into an individual file, to avoid merge mishaps, and make it hopefully easier to update and maintain.