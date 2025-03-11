# Insyde-Assignment

# AI-Powered Circuit Board Layout Optimization

This project develops an AI model for optimizing the placement of components on a circuit board based on predefined constraints. The model ensures efficient use of board space while considering power constraints and functional efficiency.

## Features
- **AI-driven layout optimization** using `MLPRegressor` from Scikit-learn
- **Circuit board component placement** (Input: board size, power constraints → Output: optimized component layout)
- **FastAPI-based API for deployment**
- **Matplotlib for visualization**
- **Google Colab-compatible setup**

## Installation
To run the project locally or in Google Colab, install the required dependencies:

```bash
pip install fastapi uvicorn numpy matplotlib scikit-learn nest_asyncio requests
```

## Running in Google Colab
1. Install dependencies:
   ```python
   !pip install fastapi uvicorn nest_asyncio scikit-learn matplotlib
   ```
2. Import and start FastAPI:
   ```python
   import nest_asyncio
   nest_asyncio.apply()
   
   from fastapi import FastAPI
   import uvicorn
   
   app = FastAPI()
   
   @app.get("/")
   def read_root():
       return {"message": "Circuit Board Layout API is running"}
   
   uvicorn.run(app, host="0.0.0.0", port=8000)
   ```
3. Use ngrok to expose the API publicly:
   ```python
   !pip install pyngrok
   from pyngrok import ngrok
   public_url = ngrok.connect(8000)
   print("Public URL:", public_url)
   ```
4. Access the FastAPI Swagger UI at: `https://your-ngrok-url/docs`

## AI Model & Dataset
- The AI model predicts optimal PCB component placements using **MLPRegressor**.
- A synthetic dataset of component positions and power constraints is generated for training.

## API Endpoints
- `GET /` → Returns a simple JSON message
- `POST /optimize_layout` → Runs the component placement optimization

## Usage
- Use a REST client (Postman/curl) or the FastAPI Swagger UI to interact with the API.
- The optimized layout is visualized using Matplotlib.

## Deployment
- Deploy using **Google Colab**, **local servers**, or **cloud platforms** (AWS, GCP, Heroku).

## Optional Enhancements
- Extend the AI model to support additional layout problems (furniture, roads, pipes).
- Improve visualization with OpenCV or interactive UI components.

## Contributing
Feel free to contribute by optimizing the layout strategy or extending API functionalities.

## License
This project is licensed under the MIT License.

