# Teaching Fair LLM

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- Git
- A Hugging Face account (free)

### Step 1: Clone This Repository
```bash
git clone git@github.com:USAFA-AI-Center/teaching_fair_llm.git
cd teaching_fair_llm
```

### Step 2: Create a Virtual Environment

**Linux/Mac:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows:**
```powershell
python -m venv .venv
.venv\Scripts\activate
```

**How do I know it worked?** You should see `(.venv)` at the beginning of your terminal prompt.

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

This installs everything you need:
- `fair-llm` - The AI framework we built for you
- `jupyter` - For running interactive notebooks
- `torch` - The deep learning library
- `transformers` - HuggingFace's model library
- And a few other helpful tools

**This might take a few minutes**

### Step 3.5: Connect Jupyter to Your Virtual Environment

**⚠️ CRITICAL STEP** - Don't skip this! This ensures Jupyter uses YOUR virtual environment (with all the packages you just installed).

```bash
# Make sure your venv is still activated (you should see "(.venv)" in your prompt)
# Then run:
python -m ipykernel install --user --name=llm-demos --display-name="Python (LLM Demos)"
```

**What does this do?** It registers your virtual environment as a "kernel" that Jupyter can use. Without this, Jupyter might use your system Python, and you'll get "Module not found" errors even though you installed everything!

### Step 4: Get Your Hugging Face Token

**Why do I need this?** Hugging Face hosts thousands of open-source AI models. To download and use them, you need a free access token (like a library card for AI models).

#### Create a Hugging Face Account
1. Go to [huggingface.co](https://huggingface.co)
2. Click **Sign Up** (top right corner)
3. Create your free account with your email
4. Verify your email address

#### Generate Your Access Token
1. Click on your **profile picture** (top right)
2. Select **Settings**
3. Click **Access Tokens** in the left sidebar
4. Click **New token**
5. Name it something like "LLM Demos"
6. Select **Read** role (sufficient for our needs)
7. Click **Generate token**
8. **IMPORTANT:** Copy your token immediately! You won't see it again.

It should look like: `hf_AbCdEfGhIjKlMnOpQrStUvWxYz1234567890`

#### Save Your Token
Create a file called `.env` in this project folder:
```bash
# In your terminal, from the project root:
echo "HUGGING_FACE_HUB_TOKEN=your_token_here" > .env
```

Or create the `.env` file manually with this content:
```
HUGGING_FACE_HUB_TOKEN=hf_YourActualTokenHere
```

**Security Note:** This `.env` file is already in `.gitignore` - it won't be committed to Git. Keep your token private!

### Step 5: Launch Jupyter Notebook
```bash
jupyter notebook
```

This will open Jupyter in your web browser. 

**Important:** Open either of the demos in the repository. Then:

1. Look at the **top right corner** of the notebook
2. Click on the kernel name (might say "Python 3" or similar)
3. Select **"Python (LLM Demos)"** from the dropdown
4. If you don't see this option, go back and make sure you completed Step 3.5!

**Why does this matter?** This ensures the notebook uses your virtual environment with all the installed packages. If you skip this, you'll get import errors!