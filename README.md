# PROJECT FLOW HOW TO MAKE 
*Put the text below into a file named **`AI_WORKFLOW.md`** inside your GitHub repository. This explains the whole concept to any developer (or future you) in plain English.* 

***

# The "Lego Method" for AI Coding 🧱

**The Golden Rule:** *Never ask the AI to build a car. Ask it to build a tire. Then ask it to build a steering wheel. Then ask it to bolt them together.*

When writing code with AI, 95% of projects fail because humans give the AI a massive instruction manual and say *"Build this."* The AI gets confused, guesses, and writes broken code. 

In this repository, we act as the **Head Architect**, and the AI acts as our **Junior Programmer**. We use **The Lego Method**. 

---

## The 4 Rules of this Repository

### Rule 1: The "Plug & Socket" Rule (No guessing)
Before you tell the AI to write a piece of code, you must tell it what the **Plug** looks like, and what the **Socket** looks like. 

* **Bad prompt:** *"Write a login system."*
* **Lego prompt:** 
  > "Write the Login module. It takes `[Email, Password]` as the input **(the plug)**. It must output `{Status: True/False, User_ID: #}` **(the socket)**. Do not write any code outside of this specific job."

Because the Plugs and Sockets are pre-agreed upon, **the code pieces are mathematically forced to fit together.**

***

### Rule 2: The "Goldfish Memory" File 
AI has the memory of a goldfish. By "Phase 4" of a project, it forgets what you agreed to in "Phase 1". 

To fix this, keep a file in the main folder called **`PROJECT_BIBLE.md`**. It should be max 15 lines long. It contains the laws of the house:

```text
1. Language: Python 3.11
2. Framework: FastAPI
3. Database: SQLite
4. Rule: Never use the 'os' library, only use 'pathlib'.
5. Rule: All dates must be in YYYY-MM-DD format.
```
**The habit:** Every time you open a new chat window with the AI, you copy-paste the `PROJECT_BIBLE` at the very top, and put your new request underneath it. 

***

### Rule 3: The "Green Light" Test
When the AI writes a piece of code (e.g., `user_login.py`), you are not allowed to move to the next phase until you pass the Green Light test. 

Immediately send the AI this prompt:
> *"Good. Now write a file called `test_user_login.py`. It should throw 3 fake users at this code, and print **'GREEN LIGHT'** if it works, or **'RED LIGHT'** if it fails."*

If the computer says Green Light, you save the file, close the chat, and move to Phase 2. If it says Red Light, you stay in that chat until it turns Green. **You never connect a Red piece to a Green piece.**

***

### Rule 4: One Chat = One Brick
* Never use the same ChatGPT/Claude chat window for more than one piece of the project. 
* Once the AI successfully codes "Phase 1", **kill that chat**. 
* Open a brand new chat for "Phase 2", paste the `PROJECT_BIBLE`, paste the code of Phase 1, and say: *"Here is our working Phase 1. Now we are building Phase 2..."* 

*(If you keep using the same chat window for 4 days, the AI's "context window" gets stuffed with old mistakes and it starts going crazy).*

***

## The Copy-Paste Master Prompt

When you are ready to build **Node X**, copy this exact template into the AI:

```markdown
I am the Architect; you are the Coder. Do not write the whole app. We are only building [NAME OF SPECIFIC PIECE].

Here is the Project Bible (The House Rules):
[PASTE BIBLE HERE]

---

Your Job for this single file:
1. What you will receive from the app: [e.g. A user's raw typed password]
2. What you must do inside the box: [e.g. Scramble it using Bcrypt]
3. What you must spit out: [e.g. A 64-character scrambled string]

Write only the code inside this box. Do not assume any external variables exist. Keep it as dumb and clean as possible.
```

***
*Credit: This repo uses the Context-Constrained Modular Prompting workflow.*
