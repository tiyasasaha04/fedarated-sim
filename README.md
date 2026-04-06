# Multi-Client Autonomous Federated Learning Simulation

## Project Overview
This feature introduces a multi-client simulation environment where independent nodes train locally and send updates to a central server.

## Core Features
* **Autonomous Aggregation:** The server automatically aggregates updates once the threshold (20 updates) is reached, removing the need for manual intervention.
* **Multi-Client Support:** Each client runs independently with a unique `client_id` and separate dataset.
* **Update Buffering:** Server maintains a `global_updates` buffer to store weights before aggregation.

## Technical Design
* **Server:** Python Flask app using `threading.Lock` for safe buffering and autonomous triggering.
* **Client:** Python script using `argparse` for ID assignment and `requests` for communication.

## How to Run
1. **Install Dependencies:** `python -m pip install -r requirements.txt`
2. **Start Server:** `python server.py`
3. **Start Clients:** `python client_sim.py --id A`, `python client_sim.py --id B`, etc.
