NO_NOKOL Plagiarism-Checker
A web application to check if a document contents are plagiarised with multiple options availaible based upon the requirements.

To run the app
run command "pip install -r requirements.txt"
run command "python app.py" in the terminal
Note1 : Make sure that python 3.8+ is installed in your system. Also installing Anaconda is recommended, if you don’t have Anaconda installed yet, follow these steps provided on the Anaconda installation page.
Note2 : Make sure that Java is installed in your machine to use the tika package
Note3 : To use the Assamese Plag-Check, follow these steps :
Get your API key and location to use the Microsoft translation API ( refer here)
Create a .env file and write this code (replace "yourAPIkey" and "yourLocation" with the one that you obtained in step i.)
API_KEY=yourAPIkey
LOCATION=yourLocation
How it works
Based on the requirements there are three approaches to this project.
It searches online using web scarapper designed to utilize Bing serarch engine for some queries. Queries are extracted from the source txt/pdf/odt/docx file.
First approach works on English extracted data.
Second approach works on Assamese data translated using Microsoft Translator api and then translated data is fed to scrapper for match.
Third approach works in a way extracted data is fed to a logic where synonyms are recoginized using NLTK Synset and then we replace the nouns and adjectives with its most commonly used synonym (obtained from NLTK brown corpus) after that matches are found using the same method.
Resulting URL, matched contents are checked for similarity with given text query.
Finally the most probable sources are displayed on views with information showing plagiarised percentage and sentences.
Required Libraries
The project uses tika module to extract text from files.
Other required libraries are:
beautifulsoup4==4.10.0
bs4==0.0.1
certifi==2021.5.30
charset-normalizer==2.0.6
click==8.0.1
colorama==0.4.4
Flask==2.0.1
idna==3.2
itsdangerous==2.0.1
Jinja2==3.0.1
joblib==1.0.1
MarkupSafe==2.0.1
nltk==3.6.3
python-dotenv==0.19.0
regex==2021.8.28
requests==2.26.0
soupsieve==2.2.1
tika==1.24
tqdm==4.62.3
urllib3==1.26.6
Werkzeug==2.0.1
Folder Structure
Static/ : Contains views functionallity logics, script and styles.
Templates/ : Contains html files for rendering on views.
app.py : Main script file for running FLask application.
modules.py : Consists of scrapper logic and required modules like tika logic for extracting text.
