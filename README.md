# Container Networking with Docker: MERN Stack Project

This project demonstrates networking between Docker containers to deploy a MERN (MongoDB, Express, React, Node.js) stack application. The services include a backend (Node.js/Express), a frontend (React) and a MongoDB database. All services are containerized and communicate over a custom Docker network.


## Prerequisites

- [Docker](https://www.docker.com/) & [Docker Compose](https://docs.docker.com/compose/) installed on the system.


## Services Overview

1. **Backend:**
   - Exposed on port `5050`.
   - Connects to MongoDB using the `MONGO_URI` environment variable.
   - Depends on the MongoDB container.

2. **Frontend:**
   - Exposed on port `5173`.
   - Communicates with the backend using the `REACT_APP_API_URL` environment variable.

3. **MongoDB:**
   - Exposed on port `27017`.
   - Data persisted locally using the `mongo-data` volume.

## Docker Compose Configuration

### Networks
- **mern_network**: A bridge network that allows inter-container communication.

### Volumes
- **mongo-data**: Used to persist MongoDB data on the host machine.

### Environment Variables
- `MONGO_URI`: Connection string for MongoDB.
- `REACT_APP_API_URL`: URL for the frontend to communicate with the backend.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/ArcusTen/CS360-Semester-Project
    cd CS360-Semester-Project
    ```

2. Build and start the containers:
   ```bash
   docker-compose up --build
   ```

3. Access the services:
   - **Frontend:** [http://localhost:5173](http://localhost:5173)
   - **Backend API:** [http://localhost:5050](http://localhost:5050)
   - **MongoDB:** Accessible on port `27017` (for development/debugging purposes).

4. To stop the services:
   ```bash
   docker-compose down
   ```

## Persistent Data

MongoDB data is persisted in the `mongo-data` volume. To clear the data, you can remove the volume:

```bash
docker-compose down -v
```

## Contributions

<table>
    <tr>
        <td align="center">
            <img src="https://github.com/kiran1500.png" alt="Kiran's Picture" width="100" height="100"><br>
            <b>Kiran Bibi</b>
        </td>
        <td align="center">
            <img src="https://github.com/OceanCurrent25.png" alt="Ifrah's Picture" width="100" height="100"><br>
            <b>Ifrah Nouman</b>
        </td>
        <td align="center">
            <img src="https://github.com/ArcusTen.png" alt="ArcusTen's Picture" width="100" height="100"><br>
            <b>Muhammad Haris</b>
        </td>
    </tr>
</table>