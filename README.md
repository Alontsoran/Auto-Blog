# WebsiteIL Blog Content Generator

This project provides a comprehensive solution for generating, saving, and managing SEO-optimized blog content using OpenAI's GPT-3.5 Turbo model. It integrates with MySQL to store blog data and saves generated content as HTML files, designed to promote your business effectively.

## Features

- Generate blog content over 1000 words using OpenAI's API.
- Structured HTML output with proper SEO tags and attributes.
- Dynamic insertion of additional messages to tailor content.
- Automatic saving of HTML files in a specified directory.
- Integration with MySQL to store blog details and content.
- Responsive and user-friendly HTML template.

## Requirements

- Python 3.6+
- `requests` library
- `mysql-connector-python` library
- OpenAI API key
- MySQL database

## Setup

1. **Clone the Repository:**

    ```sh
    git clone https://github.com/yourusername/websiteil-blog-generator.git
    cd websiteil-blog-generator
    ```

2. **Install Dependencies:**

    ```sh
    pip install requests mysql-connector-python
    ```

3. **Configure MySQL Database:**

    Create a MySQL database and table using the following schema:

    ```sql
    CREATE DATABASE your_database;

    USE your_database;

    CREATE TABLE blogs (
        id INT AUTO_INCREMENT PRIMARY KEY,
        author VARCHAR(255),
        date DATE,
        time TIME,
        description TEXT,
        content LONGTEXT,
        link VARCHAR(255)
    );
    ```

4. **Set Up Configuration:**

    Update the database configuration in the `save_to_db` function:

    ```python
    db_config = {
        "host": "localhost",
        "user": "your_username",
        "password": "your_password",
        "database": "your_database"
    }
    ```

5. **Run the Script:**

    Execute the script by running:

    ```sh
    python blog_generator.py
    ```

## Usage

1. **Generate Blog Content:**

    The script will prompt you for the blog topic and additional content. The OpenAI API will generate the blog content based on the provided inputs.

2. **Save HTML File:**

    The generated content is saved as an HTML file in the specified directory with a timestamped filename.

3. **Store in Database:**

    The blog content and HTML file link are stored in the MySQL database for easy retrieval and management.

## Example

1. **Blog Topic Input:**

    ```sh
    What is the topic of the blog? 
    ```

2. **Additional Messages Input:**

    ```sh
    Enter additional content message 1: 
    Enter additional content message 2: 
    Enter additional content message 3: 
    Enter additional content message 4: 
    ```

3. **Output:**

    ```sh
    HTML file 'blog_YYYYMMDDHHMMSS.html' created with blog content.
    Blog content and HTML link added to the database.
    ```

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact

For any questions or support, please contact [your_email@example.com](mailto:your_email@example.com).

