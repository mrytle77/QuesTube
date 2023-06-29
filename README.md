# QuesTube
A Chrome plugin that converts video transcripts to text and allows users to ask questions about the video.
Create virtual environment:
conda or mamba - I use mamba but you can use conda also. They both function the same here. Run the following command in the terminal (from the project folder) mamba env create --file env.yml and then activate the env with mamba activate QuesTube
you can also use virtualenv I will leave a requirements.txt file also
We use OpenAI's GPT3.5, you need to add your own API key. Create a .env file and add an entry as OPENAI_API_KEY="<enter-your-key-here>", save and close out of the file.
From the terminal or your IDE, run uvicorn src.main:app to start the server from which we will be making api calls
If you get port error, then run uvicorn src.main:app --port 8080 or whatever port you want to
You can also run uvicorn src.main:app --reload to run in developer mode, where any change detected will immediately be reflected
You can see the documentation on the api by visiting http://127.0.0.1:8000/redoc or http://127.0.0.1:8000/docs
To see the result, connect it up to a front end, or hit the api from curl or postman. The request will include the following:
request body {'query': "Who are some of the people mentioned in the video?"}
query parameter to be passed is video_id=<youtube_video_id> 
