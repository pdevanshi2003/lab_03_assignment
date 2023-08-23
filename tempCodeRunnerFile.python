class Flight:
    def __init__(self, flight_id, from_city, to_city, price):
        self.flight_id = flight_id
        self.from_city = from_city
        self.to_city = to_city
        self.price = price

class FlightDatabase:
    def __init__(self):
        self.flights = []

    def add_flight(self, flight):
        self.flights.append(flight)

    def search_by_flight_id(self, flight_id):
        for flight in self.flights:
            if flight.flight_id == flight_id:
                return flight
        return None

    def search_by_source_city(self, source_city):
        matching_flights = []
        for flight in self.flights:
            if flight.from_city == source_city:
                matching_flights.append(flight)
        return matching_flights

    def search_by_destination_city(self, dest_city):
        matching_flights = []
        for flight in self.flights:
            if flight.to_city == dest_city:
                matching_flights.append(flight)
        return matching_flights

def main():
    flight_db = FlightDatabase()

    # Populate the flight database
    flight_data = [
        ("AI161E90", "BLR", "BOM", 5600),
        ("BR161F91", "BOM", "BBI", 6750),
        ("AI161F99", "BBI", "BLR", 8210),
        ("VS171E20", "JLR", "BBI", 5500),
        ("AS171G30", "HYD", "JLR", 4400),
        ("AI131F49", "HYD", "BOM", 3499)
    ]

    for data in flight_data:
        flight_db.add_flight(Flight(*data))

    # User input
    print("Search by:")
    print("1. Flight ID")
    print("2. Source City")
    print("3. Destination City")
    search_choice = input("Enter your choice (1/2/3): ")

    if search_choice == "1":
        user_input = input("Enter flight ID: ")
        flight = flight_db.search_by_flight_id(user_input)
    elif search_choice == "2":
        user_input = input("Enter source city: ")
        matching_flights = flight_db.search_by_source_city(user_input)
    elif search_choice == "3":
        user_input = input("Enter destination city: ")
        matching_flights = flight_db.search_by_destination_city(user_input)
    else:
        print("Invalid choice.")
        return

    # Display results
    if "flight" in locals():
        if flight:
            print("Flight ID:", flight.flight_id)
            print("From:", flight.from_city)
            print("To:", flight.to_city)
            print("Price:", flight.price)
        else:
            print("Flight not found.")
    elif "matching_flights" in locals():
        if matching_flights:
            print("Matching flights:")
            for flight in matching_flights:
                print("Flight ID:", flight.flight_id)
                print("From:", flight.from_city)
                print("To:", flight.to_city)
                print("Price:", flight.price)
        else:
            print("No matching flights found.")

if __name__ == "__main__":
    main()