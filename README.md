# Multithreaded Flight Information System (Client-Server Architecture)

## Project Description  
This project implements a **multi-threaded server application** that fetches real-time flight data from the AviationStack API and distributes it to connected clients. The server handles multiple simultaneous client connections, processes requests for arrived/delayed flights and flight details, and gracefully manages client disconnections. Clients interact via a user-friendly GUI built with Tkinter.

---

## Semester  
Second Semester 2024/2025  

## Group  
- **Group Name**: SA11  
- **Course Code**: ITNE352  
- **Section**: 1  
- **Students**:  
  1. **ABDULRAHMAN ALKOOHEJI** (ID: 202204446)  
  2. **MOHAMED WALEED** (ID: 202108497)  

---

## Table of Contents  
1. [Requirements](#requirements)  
2. [How to Run](#how-to-run)  
3. [The Scripts](#the-scripts)  
4. [Additional Concepts](#additional-concepts)  
5. [Acknowledgments](#acknowledgments)  
6. [Conclusion](#conclusion)  
7. [Resources](#resources)  

---

## Requirements  

### Prerequisites  
- **Python 3.8+**: [Download Python](https://www.python.org/downloads/)  
- **AviationStack API Key**: [Sign up here](https://aviationstack.com/) (free tier available)  

### Setup  
1. **Clone the repository**  
   ```bash
   git clone [your-repo-url]
Install dependencies

bash
pip install -r requirements.txt  # Contains: requests==2.31.0
Add API key
Replace API_KEY in server.py (line 7) with your AviationStack key.

How to Run
Start the Server
bash
python server.py
Enter an airport ICAO code when prompted (e.g., KJFK for JFK Airport).

Run the Client
bash
python client.py
Enter a username and use the GUI to:

View arrived/delayed flights

Search for specific flight details

The Scripts
Server Script (server.py)
Main Functionalities:

Fetches flight data from AviationStack API (100 flights/request)

Handles concurrent client connections using threading

Processes 3 request types:

Arrived flights: IATA code, departure airport, arrival time/terminal/gate

Delayed flights: IATA code, delay duration, estimated arrival

Flight details: Full departure/arrival info, status, schedules

Key Packages:

socket, threading, requests, json

Client Script (client.py)
Main Functionalities:

Connects to server and sends username

Provides GUI (Tkinter) with buttons for flight queries

Displays results in a scrollable table (Treeview)

Key Packages:

socket, json, tkinter

Additional Concepts
Multithreading
The server spawns a new thread for each client connection.
Example from server.py:

python
client_thread = threading.Thread(target=handle_client, args=(conn, addr))
client_thread.start()
GUI (Tkinter)
Treeview widget for tabular flight data display

Dialog boxes for username input and flight code queries

Acknowledgments
AviationStack for providing flight data API

Dr. Mohammed Almeer for project guidance

Python Documentation for socket/threading references

Conclusion
This project demonstrates:
✅ Network programming: TCP sockets, client-server architecture
✅ Concurrency: Multithreaded request handling
✅ API integration: Real-time flight data retrieval
✅ GUI development: User-friendly Tkinter interface

Future Enhancements:

SSL encryption for secure communication

Expanded error handling for API failures

Resources
AviationStack API Docs

Python Socket Programming

Tkinter GUI Guide
