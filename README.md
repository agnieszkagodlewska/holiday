# holiday
This program calculates a user’s holiday cost including the plane cost, hotel cost, and car rental cost.

# The list of avaiable cities.
cities = ['Faro', 'Nicea', 'Malaga', 'Barcelona', 'Madrid', 'Funchal', 'Ibiza', 'Gdansk']

# The list of cities with flights cost.
flight_cost = {'Faro': 180,
               'Nicea': 225,
               'Malaga': 210,
               'Barcelona': 250,
               'Madrid': 230,
               'Funchal': 320,
               'Ibiza': 195,
               'Gdansk': 175}

# The user chooses the city where wants to flight for holiday
city_flight = input("Which city would you like to fly from the list?\n "
                     + 'Faro\n'
                     + 'Nicea\n'
                     + 'Malaga\n'
                     + 'Barcelona\n'
                     + 'Madrid\n'
                     + 'Funchal\n'
                     + 'Ibiza\n'
                     + 'Gdansk\n').capitalize()

# Check that chosen city is on the list.
if city_flight not in cities:
    print("Sorry, that city is not a valid option.")
    exit()

# The user chooses the numers of nights at a hotel and number of days of car rental.

while True:
    try:
        num_nights = int(input('The number of nights you will be staying at a hotel: '))
        rental_days = int(input('The number of days that you will be hiring a car for: '))
        break
    except ValueError:
        print("Oops! That was not a valid number. Try again...")

# Calculation of hotel cost, plane cost, car rental and total cost of holiday..


def hotel_cost(num_nights):
    return 100*num_nights


def plane_cost():
    return flight_cost[city_flight]


def car_rental(rental_days):
    return 50*rental_days


def holiday_cost(hotel_cost, plane_cost, car_rental):
    return hotel_cost(num_nights) + plane_cost() + car_rental(rental_days)


# Print out all the details about the holiday.
print(f"\nThe total cost of yours holiday is £{holiday_cost(hotel_cost, plane_cost, car_rental)}.\n")
print('The cost of holiday included:')
print(f"- the fligtht to {city_flight} (£{plane_cost()}).")
print(f"- the hotel for {num_nights} nights (£{hotel_cost(num_nights)}).")
print(f"- the car rental for {rental_days} days (£{car_rental(rental_days)}).")
