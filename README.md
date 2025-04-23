# BeRAM Website

Official website for BeRAM - Bhandarkar Excellences of Research and Management.

## Features

- Responsive design for all devices
- Project showcase
- Solutions overview
- News and updates
- Contact form with email integration
- Mission statement page

## Technology Stack

- **Backend**: Flask (Python)
- **Frontend**: HTML, CSS, JavaScript, Bootstrap 5
- **Email**: Flask-Mail with Gmail SMTP
- **Production Server**: Gunicorn, Nginx
- **Containerization**: Docker, Docker Compose
- **Testing**: Pytest

## Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/beram-website.git
   cd beram-website
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.env` file:
   ```bash
   cp .env.example .env
   ```
   Then edit the `.env` file to add your configuration.

5. Run the development server:
   ```bash
   python run.py
   ```

6. Visit http://localhost:5000 in your browser.

## Testing

Run tests with pytest:
```bash
pytest
```

For coverage report:
```bash
pytest --cov=beram
```

## Production Deployment

### Using Docker

1. Build and start the containers:
   ```bash
   docker-compose up -d
   ```

2. The application will be available at http://localhost:80

### Manual Deployment

1. Set up a production server with Python, Nginx, and Gunicorn.

2. Clone the repository to `/var/www/beram`.

3. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

5. Create a `.env` file from `.env.production`:
   ```bash
   cp .env.production .env
   ```
   Then edit the `.env` file with your production settings.

6. Set up the systemd service:
   ```bash
   sudo cp beram.service /etc/systemd/system/
   sudo systemctl daemon-reload
   sudo systemctl enable beram
   sudo systemctl start beram
   ```

7. Configure Nginx:
   ```bash
   sudo cp nginx_beram.conf /etc/nginx/sites-available/beram
   sudo ln -s /etc/nginx/sites-available/beram /etc/nginx/sites-enabled/
   sudo nginx -t
   sudo systemctl restart nginx
   ```

8. Set up SSL with Let's Encrypt:
   ```bash
   sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com
   ```

## License

All rights reserved. This project is proprietary and confidential.

## Contact

For inquiries, please contact: Contactberam@gmail.com
