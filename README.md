# Teaching Fair LLM

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- Git
- A Hugging Face account (free)

### Step 1: Clone This Repository
```bash
git clone git@github.com:USAFA-AI-Center/teaching_fair_llm.git
cd llm-math-demo
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
python -m ipykernel install --user --name=llm-math-demo --display-name="Python (LLM Demos)"
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
5. Name it something like "LLM Math Demo"
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

**Important:** Navigate to `math_demo.ipynb` and open it. Then:

1. Look at the **top right corner** of the notebook
2. Click on the kernel name (might say "Python 3" or similar)
3. Select **"Python (LLM Math Demo)"** from the dropdown
4. If you don't see this option, go back and make sure you completed Step 3.5!

**Why does this matter?** This ensures the notebook uses your virtual environment with all the installed packages. If you skip this, you'll get import errors!

## 🛠️ Troubleshooting

### "Kernel Not Found" or Wrong Kernel in Jupyter
If you don't see "Python (LLM Math Demo)" in the kernel selector, or the notebook won't connect:

```bash
# Make sure venv is activated (you should see "(venv)" in your prompt)
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows

# Reinstall ipykernel
pip install ipykernel

# Register the kernel again
python -m ipykernel install --user --name=llm-math-demo --display-name="Python (LLM Math Demo)"

# Restart Jupyter completely
# Press Ctrl+C in the terminal where Jupyter is running
# Then launch it again: jupyter notebook
```

After restarting, open the notebook and select the correct kernel from the top right.

### "Module not found" Error
This almost always means Jupyter is using your system Python instead of your virtual environment:

**Solution 1 - Check your kernel:**
1. In the notebook, look at top right corner
2. Click the kernel name
3. Select "Python (LLM Math Demo)"

**Solution 2 - Verify packages in venv:**
```bash
# Make sure venv is activated
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows

# Check if packages are installed
pip list | grep fair-llm
pip list | grep transformers

# If missing, reinstall
pip install -r requirements.txt
```

**Solution 3 - Nuclear option (start fresh):**
```bash
# Deactivate current venv
deactivate

# Remove old venv
rm -rf venv  # Mac/Linux
rmdir /s venv  # Windows

# Start over from Step 2 in the README
```

### Virtual Environment Not Activated
Make sure your virtual environment is activated before running ANY commands:
```bash
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
```

You should see `(venv)` at the beginning of your terminal prompt.

If you don't see it, the venv is not activated!

### "Authentication Failed" Error
- Check that your `.env` file exists in the project root
- Verify your token is correct (no extra spaces!)
- Make sure the token has at least **Read** permissions
- Try generating a new token if needed

### Jupyter Won't Open
Make sure Jupyter is installed in your virtual environment:
```bash
pip install jupyter
jupyter notebook
```

### Model Download is Slow
Don't worry! The first time you run the notebook, it needs to download the LLM (about 1-2 GB). This is normal and only happens once. Future runs will be much faster.

### "CUDA/GPU Not Found" Warning
This is fine! The demo will automatically use your CPU. It might be a bit slower, but it will work perfectly.
