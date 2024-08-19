# My Dapp

My Dapp เป็นแอปพลิเคชันกระจายศูนย์ (Decentralized Application) ที่สร้างขึ้นด้วย Vue.js สำหรับ frontend, Solidity สำหรับ Smart Contract, และ Node.js สำหรับ backend โดยใช้ Docker สำหรับการ deploy

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Smart Contracts](#smart-contracts)
- [Docker](#docker)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Frontend**: สร้างด้วย Vue.js สำหรับการจัดการ UI ของ Dapp
- **Backend**: ใช้ Node.js และ Express สำหรับ API และการเชื่อมต่อกับ Smart Contracts
- **Smart Contracts**: พัฒนาและ deploy บน Ethereum blockchain ด้วย Solidity
- **Docker**: ใช้ Docker สำหรับการ deploy แอปพลิเคชันบน cloud

## Prerequisites

ก่อนที่จะเริ่มต้นใช้งานโปรเจกต์นี้ คุณต้องติดตั้งสิ่งต่อไปนี้:

- [Node.js](https://nodejs.org/en/) (v14 ขึ้นไป)
- [npm](https://www.npmjs.com/) หรือ [Yarn](https://yarnpkg.com/)
- [Docker](https://www.docker.com/) และ [Docker Compose](https://docs.docker.com/compose/)
- [MetaMask](https://metamask.io/) สำหรับเชื่อมต่อกับ Ethereum network

## Installation

1. **Clone the repository:**
```sh
   git clone https://github.com/Phanurat/dapp-w3.git
   cd my-dapp
```

2. **Install frontend dependencies:**
```sh
    cd client
    npm install
```

3. **Install backend dependencies:**
```sh
    cd ../backend
    npm install
```

4. **Compile smart contracts:**
```sh
npx hardhat compile
```
## Usage

1. **Running the application locally:**
```sh
cd backend
npm start
```

2. **Start the frontend development server:**

```sh
cd ../client
npm run serve
```
## Smart Contracts

1. **Deploy smart contracts:**
```sh
npx hardhat run scripts/deploy.js --network rinkeby
```
2. **Interact with contracts:**

## Docker

1. **Build the Docker image:**

```sh
docker build -t my-dapp .
```
2. **Run the application using Docker:**

```sh
docker run -p 80:80 my-dapp
```

3. **Using Docker Compose:**

```sh
docker-compose up
```