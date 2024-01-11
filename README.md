
# SSI_dApp

<div align="center">
  <p>
    <strong>SSI_dApp</strong> is a decentralized application designed for managing users' digital identity using the Self Sovereign Identity (SSI) method. This stand-alone application is optimized for independent use, yet it seamlessly integrates with the Data Cellar project, enhancing its capabilities in digital identity management.
  </p>
</div>

## Table of Contents
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
- [Running the Application](#running-the-application)
  - [Starting the Frontend](#starting-the-frontend)
  - [Starting the Backend](#starting-the-backend)
- [License](#license)

## Getting Started

### Prerequisites

Before installing the SSI_dApp, ensure you have the following tools installed on your system:

- `mkcert`
- `OpenSSL`
- `npm` (Node Package Manager)

### Installation

#### Installing `mkcert`

Install `mkcert` on your system based on your operating system:

- **Linux**
  ```bash
  sudo apt-get install libnss3-tools
  ```

- **MacOS**
  ```bash
  brew install mkcert
  ```

- **Windows**
  ```bash
  choco install mkcert
  ```

#### Installing `OpenSSL`

Install `OpenSSL` using the following commands:

- **Linux**
  ```bash
  sudo apt-get install openssl
  ```

- **MacOS**
  ```bash
  brew install openssl
  ```

- **Windows**
  ```bash
  choco install openssl
  ```

### Configuration

#### Creating Certificates for the Backend

Navigate to the backend directory and create certificates:

```bash
cd backend
mkcert -key-file key.pem -cert-file cert.pem localhost
cd ..
```

#### Creating Certificates for the Frontend

Generate the necessary certificates for the frontend:

```bash
cd frontend
mkcert -key-file key.pem -cert-file cert.pem localhost
openssl x509 -in cert.pem -out cert.crt
openssl rsa -in key.pem -out key.key
cd ..
```

#### Installing dependencies

Install the necessary dependencies for both the frontend and backend:

```bash
cd frontend
npm install
cd ..
cd backend
npm install
```

## Running the Application

Open two separate terminal windows or tabs: one for running the frontend and another for the backend.

### Starting the Frontend

In the frontend directory, start the application:

```bash
cd frontend
npm start
```

### Starting the Backend

Similarly, in the backend directory, start the server:

```bash
cd backend
node server.js
```

## License

This project is licensed under the [MIT License](./LICENSE). For more details, please refer to the [LICENSE](./LICENSE) file.
