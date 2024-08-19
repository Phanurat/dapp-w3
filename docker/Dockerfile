# ใช้ base image เป็น Node.js สำหรับ backend
FROM node:16-alpine AS backend

# ตั้งค่า working directory
WORKDIR /app/backend

# คัดลอกไฟล์ package.json และ package-lock.json
COPY backend/package*.json ./

# ติดตั้ง dependencies
RUN npm install

# คัดลอกโค้ดทั้งหมด
COPY backend/ .

# Build backend (ถ้ามี)
# RUN npm run build

# ใช้ base image เป็น Node.js สำหรับ frontend
FROM node:16-alpine AS frontend

# ตั้งค่า working directory
WORKDIR /app/frontend

# คัดลอกไฟล์ package.json และ package-lock.json
COPY client/package*.json ./

# ติดตั้ง dependencies
RUN npm install

# คัดลอกโค้ดทั้งหมด
COPY client/ .

# Build frontend
RUN npm run build

# ตั้งค่า Nginx เพื่อเสิร์ฟไฟล์ static ของ frontend
FROM nginx:alpine

# คัดลอกไฟล์ frontend ที่ถูก build ไปยัง Nginx
COPY --from=frontend /app/frontend/dist /usr/share/nginx/html

# คัดลอกไฟล์ backend ที่ถูก build
COPY --from=backend /app/backend /app/backend

# เปิดพอร์ต 80 สำหรับ Nginx
EXPOSE 80

# เริ่มรัน Nginx และ backend server
CMD ["nginx", "-g", "daemon off;"] 