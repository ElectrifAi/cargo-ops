# Input/Output Description

- Input: A zip file containing 2 comma separated (csv) files. **__Reference file: sample.zip__**
- Details for each csv file:
    cargo_manifest.csv (required)
        Required columns:
            flight_id: Unique identifier for each flight
            cargo_id: Unique identifier for each cargo item
            weight: Weight of the cargo item
            volume: Volume of the cargo item
            destination: Destination airport code
            priority: Priority status of the cargo item
            booking_date: Date when the cargo was booked
            cargo_type: Type of cargo being transported

    flight_capacity.csv (required)
        Required columns:
            flight_id: Unique identifier for each flight
            max_weight_capacity: Maximum weight capacity for the flight
            max_volume_capacity: Maximum volume capacity for the flight
            departure_time: Scheduled departure time
            arrival_time: Scheduled arrival time
            origin: Origin airport code
            destination: Destination airport code
            aircraft_type: Model of the aircraft


## Output

- Output: A JSON list of objects containing the optimized cargo load for each flight.
    Fields:
        flight_id: Unique identifier for each flight
        cargo_load: Array of cargo IDs optimized for weight and volume
        total_weight: Total weight of the optimized cargo
        total_volume: Total volume of the optimized cargo
        unused_weight_capacity: Remaining weight capacity after optimization
        unused_volume_capacity: Remaining volume capacity after optimization
