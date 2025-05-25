
# MID AI – Internship Take-Home Project

This repository holds all deliverables for the MID AI Internship Take-Home Task. The project is divided into three main sections:

1. **Computer Vision (YOLO + OpenCV)** – Perform object detection and annotation on images or videos.
2. **Natural Language Processing (LLM)** – Convert a construction specification text into a structured JSON format.
3. **Dockerization** – Package the entire workflow (from detection to JSON extraction) into a single Docker container for consistency and portability.

---

## Project Structure


├── results/

│   ├── annotated_image_or_video.png   # Output from Object Detection (Part 1)

│   ├── specifications.json            # Output from Text-to-JSON Extraction (Part 2)

├── part1_summary.txt                  # Description and notes on Part 1

├── part2_summary.txt                  # Description and notes on Part 2

├── part3_summary.txt                  # Docker configuration details

├── Dockerfile                         # Defines the Docker container

├── requirements.txt                   # Lists Python libraries required

├── generate_output.py                 # Script that runs the entire workflow

└── README.md                          # Project overview (this file)


---

## Running the Project with Docker

To recreate the outputs (image annotation and JSON specification), run the following commands:

```bash
docker build -t mid-ai-assignment .
docker run --rm -v $(pwd):/app mid-ai-assignment

These commands will build and execute the full pipeline inside a container, saving the results in the results/ directory of your local project.


Key Components

Part 1 leverages a pre-trained YOLO model (from the ultralytics package) alongside OpenCV to identify objects and draw bounding boxes.


Part 2 uses a large language model (LLM) with a crafted prompt to extract details like material type, thickness, function, and standards into a structured JSON format.


Part 3 integrates everything into a Docker container, ensuring reproducibility and ease of use across different environments.



Additional Information

Detailed explanations and reflections are provided in part1_summary.txt, part2_summary.txt, and part3_summary.txt.


An LLM endpoint (e.g., OpenAI API or a local model) is required to complete the text extraction.


To test with your own files, replace the input media and spec document in the /app directory.



The repository is fully self-contained and ready to execute.