# Doctor Recommendations System
## About
The goal is to create a Doctor Recommendation System that assists users by analyzing their symptoms, utilizing mock symptom data and healthcare provider databases. This system will recommend doctors based on their specialties that align with the user's needs. The solution involves leveraging data about symptoms and healthcare providers, implementing matching algorithms, and integrating user feedback to enhance the accuracy of recommendations. The system aims to improve access to healthcare services by connecting users with appropriate doctors efficiently and effectively.

## Steps for Running the Project

```
git clone https://github.com/22116001/Doctor-Recommended-System.git
cd Doctor-Recommended-System
```

### Building the project using docker

- Building:
```
sudo docker build -t backend:latest -f Dockerfile .
```
- Running the project:
```
sudo docker run -p 8000:8000 backend:latest
```

### Run without docker on local machine
We will use python's virtual environment.
**Your python version should be 3.8.x**
Follow the steps below:
```
python3.8 -m venv <name here>
source ./<name here>/bin/activate
pip install -r requirements.txt
python -m spacy download en_core_web_md
python -m pip install https://s3-us-west-2.amazonaws.com/ai2-s2-scispacy/releases/v0.5.1/en_core_sci_md-0.5.1.tar.gz
cd Doctor-Recommended_System
python manage.py runserver
```

## How to use

- Send POST Request to this endpoint
    ```
    http://0.0.0.0:8000/api/recommend-doc
    ```
- Sample Input
    ```
    {
        "symptoms" : "leg pain with difficulty to walk"
    }
    ```
- Sample Output
    ```
   {
    "data": 
        [
            {
            "Osteoarthristis": "Rheumatologist"
            },
            {
            "Arthritis": "Rheumatologist"
            }
        ]
    }
    ```