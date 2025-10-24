# 🧮 Can LLMs Do Math? - Hands-On Demo

Welcome to your first hands-on exploration of Large Language Models! In this demo, you'll discover firsthand whether LLMs can truly "do" math, or if something else is going on under the hood.

## 🎯 What You'll Learn

By the end of this demo, you'll understand:
- ✅ How LLMs handle mathematical operations
- ✅ The difference between **pattern matching** and **computing**
- ✅ Why LLMs succeed on simple math but struggle with complex calculations
- ✅ The fundamental limitation: **prediction vs. calculation**

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

It should look like: `hf_AbCdEfGhIjKlMnxxxxxxxxxxx`

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

This will open Jupyter in your web browser. Navigate to `math_demo.ipynb` and open it!

## 📓 The Demo Notebook

The notebook (`math_demo.ipynb`) walks you through several experiments:

### Experiment 1: Simple Math (Pattern Matching Territory)
You'll test the LLM on common arithmetic problems:
- `2 + 2 = ?`
- `10 × 10 = ?`
- `5² = ?`

**Question to think about:** Why does the LLM succeed here?

### Experiment 2: Complex Math (Beyond Memorization)
You'll test the LLM on uncommon calculations:
- `8,347 × 6,291 = ?`
- `237 × 843 = ?`

**Question to think about:** What happens when the pattern isn't in the training data?

### Experiment 3: The Reveal
You'll see the attention mechanism in action and understand what the LLM is *actually* doing when it "solves" math problems.

## 🤔 Discussion Questions

As you work through the notebook, consider:

1. **Is the LLM calculating or pattern-matching?**
2. **What's the difference between predicting text and computing results?**
3. **Why does the LLM do well on common problems but fail on uncommon ones?**
4. **If you wanted a reliable AI math assistant, what would you need to add?**

## 🛠️ Troubleshooting

### "Module not found" Error
Make sure your virtual environment is activated:
```bash
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
```

Then reinstall:
```bash
pip install -r requirements.txt
```

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

## 📚 What's Next?

After completing this demo, you'll understand:
- ✅ The fundamental limitation of pure language models
- ✅ Why we need **agents** (LLMs + tools) for reliable computation
- ✅ The difference between statistical prediction and algorithmic computation

In the next class, we'll explore how to give LLMs actual tools (like calculators, databases, and APIs) to overcome these limitations!