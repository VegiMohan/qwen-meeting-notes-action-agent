# qwen-meeting-notes-action-agent
AI meeting notes agent powered by Qwen2.5-3B-Instruct that converts meeting transcripts into summaries, decisions, and structured action items with owners and due dates.

## Tradeoffs and Limitations

I chose Qwen2.5-3B-Instruct because it can run locally in Google Colab using a free T4 GPU, so I did not need a paid API.

I kept the approach simple and used prompting instead of fine-tuning because the goal was to build a working agent within the 24-hour challenge.

The agent returns JSON because it makes the summaries and action items easy to save and reuse.

The main limitation is that a smaller model can sometimes miss an action item or misunderstand an owner or deadline. With more time, I would add better validation, confidence scores, and support for longer or more complex meeting transcripts.

## Setup and Usage

This project runs in Google Colab using the Qwen2.5-3B-Instruct open-source model. No API key is required.

### 1. Open the notebook

Open `meeting_agent.ipynb` in Google Colab.

### 2. Enable GPU

In Colab, select:

Runtime → Change runtime type → T4 GPU

### 3. Run the notebook

Run the cells from top to bottom.

The notebook installs the required Python packages, downloads Qwen2.5-3B-Instruct, and loads the model.

### 4. Upload meeting transcripts

Upload one or more `.txt` meeting transcript files when prompted.

### 5. View the results

The agent extracts:

- Meeting summary
- Key decisions
- Action items
- Owner
- Due date

The results are returned as JSON and saved in the `Example Outputs` format.
