### **Project README**

# Imagination in translation
An interactive experiment for studying the gap between semantic and visual representations in humans and AI.

## Project Description
The project investigates whether humans can accurately convey mental images to an AI solely through language. Participants are asked to describe verbally a ground-truth image to a Stable Diffusion model, which then generates an image based on the description. After each generation, a VGG16-based visual similarity score is displayed alongside the subjective similarity assessment by the participants, who can either accept the generation (if they believe the similarity is sufficient) or refine their description and generate a new image. The number of refinement trials is limited to five for each ground truth image. It is not possible to use the same description twice without changes.

The data for all generation attempts (e.g., text descriptions, generated images, similarity scores) as well as the model parameters (e.g. seed) are logged for later analysis of language-to-vision alignment.

## Core Components
- Local Stable Diffusion 3.5 Large Turbo [model](https://platform.stability.ai/docs/api-reference#tag/Generate/paths/~1v2beta~1stable-image~1generate~1sd3/post) for image generation
- [Streamlit](https://streamlit.io/)-based user interface
- [VGG16](https://arxiv.org/abs/1409.1556)-based visual similarity analysis
- Logging of all sessions, iterations and generated pictures
- Data processing

## Setup Instructions
1. Open the terminal.
2. Check your Python version. For certain packages (e.g. PyTorch) you need Python 3.11 or lower (but higher than Python 3.7).
```bash
# Windows
python --version
````  
```bash
# Linux / macOS
python3 --version
````
3. If the version is correct, clone the repository.
```bash
git clone https://github.com/AnatKordon/Imagination_in_translation.git
cd Imagination_in_translation
````
4. Set up a Python virtual environment.
```bash
# Linux / macOS
python3 -m venv .venv
source .venv/bin/activate
````
```bash
# Windows PowerShell
python -m venv venv
venv\Scripts\Activate
````
5. Install the dependencies:
```bash
pip install -r requirements_dev.txt
````
6. Create manually a file called .env in the project root and add your Stability AI API key (do not share the key)
```bash
STABILITY_API_KEY=your_stability_ai_key_goes_here
```` 
7. Run the Streamlit app.
```bash
streamlit run ui/ui.py
```` 
## License
MIT – see `LICENSE` for full text.

## Authors
Anat Korol Gordon

Itai Peleg

Maayan Shirizly

Nataliya Kalanova

Sivan Flomen

Yaniv Kopelman

## Contacts 
If you have any questions, suggestions or bug reports, please feel free to reach out at **anat.korol@gmail.com** (Anat Korol Gordon).
