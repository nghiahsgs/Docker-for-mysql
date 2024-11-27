# Tạo volume cho MySQL
docker volume create mysql_data

# Chạy container MySQL với các cấu hình cơ bản
docker run -d \
    --name mysql_container \
    -e MYSQL_ROOT_PASSWORD=your_root_password \
    -e MYSQL_DATABASE=your_database \
    -e MYSQL_USER=your_username \
    -e MYSQL_PASSWORD=your_password \
    -p 3310:3306 \
    -v mysql_data:/var/lib/mysql \
    mysql:latest

# Kiểm tra container đang chạy
docker ps

# Để kết nối vào MySQL container
docker exec -it mysql_container mysql -u root -p

# connection string
mysql://your_username:your_password@localhost:3310/your_database
