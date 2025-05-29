## 🌟 About The Project

This project is a static HTML celebration page, served by an **Apache web server running inside a Docker container**. The entire setup is managed using **Docker Compose** for easy startup and configuration.

## 🚀 How To View

Follow these steps to get your celebration page up and running:

**Prerequisites:**
* Make sure you have [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your system.

**Steps:**

1.  **Clone this repository:**
    ```bash
    git clone https://github.com/ArrozbR/docker-html-project.git
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd docker-html-project/
    ```
3.  **Start the Apache server using Docker Compose:**
    This command will build (if necessary) and start the Apache service in detached mode.
    ```bash
    docker compose up -d
    ```
4.  **Copy your website file to the Apache server:**
    This step ensures your `index.html` is in the correct directory within the running Apache container. (Make sure your service in `docker-compose.yml` is named `apache` or adjust the command accordingly).
    ```bash
    docker compose cp ./website/index.html apache:/usr/local/apache2/htdocs/index.html
    ```
    * **Note:** If your `docker-compose.yml` already uses a volume to map your `./website` directory directly to `/usr/local/apache2/htdocs/`, this manual `cp` step might only be needed for updates if the file changes after the container has started, or it might not be needed at all for the initial view.

5.  **Open your browser and celebrate!**
    Navigate to `http://localhost` or `http://localhost:80`

6.  **To stop the services:**
    ```bash
    docker compose down
    ```