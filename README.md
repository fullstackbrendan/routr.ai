
# Routr.ai

Routr.ai ~ https://www.routr.ai ~ built with Django, Python and HTML, is designed to manage, track, and report driver trip and fuel purchase records. It utilizes OpenAI’s API to integrate AI-driven route calculations and geolocation services, optimizing transportation logistics and fuel management.


## Screenshots

<img width="1440" alt="Screenshot 2024-08-03 at 3 18 05 PM" src="https://github.com/user-attachments/assets/0a15bcb9-a5e8-42d2-aefa-fb6f35bbf033">


## Features

- AI Integration: Utilize OpenAI’s API for intelligent route calculations.
- Driver Trip Records Management: Add, edit, view, and delete driver trip records with detailed information.
- Reporting and Exporting: Generate detailed trip reports and export them to PDF.
- Dynamic Form Management: Easily manage multiple stops within a trip.
- Light/Dark Mode Toggle: Switch between light and dark themes for better usability in different lighting conditions.
- Responsive Design: Ensure usability across different devices with a bare-bones yet user-friendly interface.
- Fuel Purchase Records Management: Log and manage fuel purchases with comprehensive details.


## Tech Stack
	
   **Backend:** Django, Python
	
   **Frontend:** HTML
	
   **APIs:** OpenAI API
	
   **Database:** SQLite (development), PostgreSQL (production)


## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/fullstackbrendan/routr.ai
   cd routr.ai 

2. Create and activate a virtual environment":
    ```bash
    python -m venv venv
    source venv/bin/activate   # On Windows: venv\Scripts\activate

3. Install dependencies:
    ```bash
    pip install -r requirements.txt

4. Set up the databases:
    ```bash
    python manage.py migrate

5. Run the development server:
    ```bash
    python manage.py runserver
## API Reference

### OpenAI API

#### Calculate Route

```http
  POST /api/calculate_route
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your OpenAI API key |
| `start_location` | `string` | **Required**. The starting location address |
| `end_location` | `string` | **Required**. The ending location address |
| `intermediate_stops` | `array` | **Optional**. Array of intermediate stop addresses |

#### Example Request Body

```json
{
  "api_key": "your_google_maps_api_key",
  "origins": ["123 Main St, Springfield, IL"],
  "destinations": ["456 Elm St, Shelbyville, IL", "789 Oak St, Capital City, IL"]
}
```

#### Example Response

```json
{
  "route": [
    "123 Main St, Springfield, IL",
    "789 Oak St, Capital City, IL",
    "456 Elm St, Shelbyville, IL"
  ],
  "distance": "150 miles",
  "duration": "2 hours 30 minutes"
}
```

## Deployment

#### To deploy Routr.ai on PythonAnywhere, follow these steps:

1.	Sign Up and Log In:
	•	Go to [PythonAnywhere](https://www.pythonanywhere.com) and create an account or log in if you already have one.

2.	Set Up a New Web App:
	•	Go to the “Web” tab and click “Add a new web app.”
	•	Choose “Manual configuration” and select the appropriate Python version (e.g., Python 3.8).

3.	Clone Your Repository:
	•	Open a Bash console from the “Consoles” tab.
	•	Clone your Git repository:
```bash
  git clone https://github.com/fullstackbrendan/routr.ai
  cd routr.ai
```

4.	Create a Virtual Environment:
	•	Create and activate a virtual environment:
```bash
  python -m venv venv
  source venv/bin/activate
```

5. Install Dependencies:
	•	Install the required packages:
```bash
  pip install -r requirements.txt
```

6. Set Up Environment Variables:
	•	In the “Web” tab, go to the “Environment variables” section and add your environment variables:
```env
  SECRET_KEY=your_secret_key
  DEBUG=False
  ALLOWED_HOSTS=your-username.pythonanywhere.com
  OPENAI_API_KEY=your_openai_api_key
  DATABASE_URL=your_database_url
```

7. Configure WSGI:
    	•	In the “Web” tab, click on the “WSGI configuration file” link.
	•	Edit the WSGI file to point to your Django project:
    ```python
    import os
    import sys
    ```

#### Add your project directory to the sys.path
project_home = '/home/your-username/routr'
if project_home not in sys.path:
    sys.path = [project_home] + sys.path

#### Set environment variable for Django settings module
os.environ['DJANGO_SETTINGS_MODULE'] = 'routr.settings'

#### Activate your virtual environment
activate_this = '/home/your-username/routr/venv/bin/activate_this.py'
with open(activate_this) as file_:
    exec(file_.read(), dict(__file__=activate_this))

#### Import Django's WSGI handler and set it as the application callable
from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()

8. Set Up the Database:
    
    •	Run the following commands in the Bash console to set up the database:
    ```bash
    python manage.py migrate
    python manage.py createsuperuser
    ```

9. Collect Static Files:

    •	Collect static files to be served:
    ```bash
    python manage.py collectstatic
    ```

10. Reload the Web App: 

    •	Go to the “Web” tab and click the “Reload” button to restart your web application.

## License

This project is licensed under the MIT License. [MIT](https://choosealicense.com/licenses/mit/)


## Authors

Brendan Enang

- GitHub: [@fullstackbrendan](https://www.github.com/fullstackbrendan)
- LinkedIn: 


## Acknowledgements

 - Underdog Devs

