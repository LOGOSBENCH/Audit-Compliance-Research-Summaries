# What Makes AI Safe? A Look Inside Technical Governance

*Reflecting on “Open Problems in Technical AI Governance” (Reuel et al., 2024)*

AI is moving faster than rules can keep up. While people argue over regulation, another question is starting to take shape: What does responsible AI look like from a technical point of view?

This post looks at the idea of *Technical AI Governance* (TAIG), presented in Reuel et al.’s paper. TAIG treats AI responsibility as an engineering problem—something we need to build into the system from the start.

The authors break AI into four technical layers—data, compute, models, and deployment—and list seven key things we should design for: **assessment, access, verification, security, operationalization, ecosystem monitoring**, and **systemic interventions**. In this post, I focus on just one: **assessment**—the challenge of understanding what’s really happening inside these systems, from harmful data patterns to risky model behavior.

If you’re building or using AI, you’re already helping shape how it affects people. The paper suggests we should take that role seriously—and build safety into the process, not tack it on afterward.

---

###  Assessment: How Do We Know If AI Is Safe?

Before a car can go on the road, it has to pass safety checks—like working brakes and functioning headlights. The same idea applies to AI. Before an AI system is used in the real world, we need to test it. Does it lie? Does it discriminate? Could it cause harm? This kind of testing is called assessment, and it’s becoming one of the most important parts of AI governance.

Some governments, like those in the U.S. and UK, already require certain kinds of assessments. One example is red-teaming—where people try to trick the AI into doing something harmful, just to see how it reacts. But there’s a problem: good assessments are still very difficult to do. They take time, money, and expertise. In many ways, assessment today feels more like an art than a science.

---

###  What Are We Looking For?

The goal of assessment is to catch problems before they reach the public. Some of the key risks include:

- AI spreading false or misleading information  
- Bias against people based on race, gender, or other identities  
- AI generating harmful, illegal, or violent content  

But the field is still very new. We don’t yet have standard tools or clear steps for how to assess these systems properly. One especially hard part is testing the data the AI was trained on—because if the data is flawed, the AI’s behavior will be too.

---

###  The Data Problem

You can think of training data like ingredients in a recipe. If the ingredients are bad—rotten or  toxic, or stolen—the final result will be harmful too. The same happens with AI. If we feed it outdated, biased, or illegal data, it will likely produce harmful outputs.

Researchers are asking important questions:

- How can we find harmful data hidden in huge datasets?  
- Can we stop illegal content before it’s used to train AI?  
- What if we don’t even have access to the training data at all?

---

###  Why Data Goes Wrong

There are two big types of bad data that show up in AI systems:

- **Legal or Ethical Risks** – This includes private personal information, hate speech, or content that breaks copyright laws.  
- **Low-Quality or Biased Data** – This can be false facts, poor translations, or data that only shows one point of view.

The tricky part is that these problems often aren’t obvious. Sometimes it’s just a small sentence or a subtle bias—but those details can still have big effects.

---

### Three Big Problems in Data Assessment

**1. 🚨 Detecting Bad Data (When We Have Access)**  
Even when researchers can see the dataset, it’s hard to say what counts as “bad.” Is it a fake quote? A borderline offensive joke? We need smarter tools that can detect these subtle issues—like hidden bias, tone, or unclear copyright problems.

**2.  Detecting Bad Data (When We Don’t Have Access)**  
In many cases, the dataset is private. That means researchers have to look at how the AI behaves, and guess what kind of data it was trained on. But this is unreliable—we’re testing the symptoms, not the source.

**3.  Provenance: Where Did That Come From?**  
Let’s say an AI says something toxic. Where did it learn that? This is the provenance problem—tracing the AI’s output back to the original data. Right now, we don’t have strong tools for this. Without knowing the source, it’s hard to fix the real issue.

---

###  Deeper Into the Data Problems: Size, Tools, and Tracing

####  The Challenge of Huge Datasets  
Modern AI models are trained on massive datasets—sometimes including trillions of words from books, websites, news, and social media. That’s what makes them fluent and useful. But it raises big questions:

- What’s actually inside these datasets?  
- Can we clean or trace them?  
- Who decides what should be included?  

These are technical problems that researchers are still working to solve.

---

####  How Do We Analyze Massive Datasets?

Working with large AI datasets is incredibly challenging. Here are three main technical hurdles:

** 1. Automating Metadata Collection**  
Metadata means “data about the data”—like where something came from, who created it, and whether it’s legal to use. Many training datasets have missing or unclear metadata, which makes ethical use difficult. Automating this process would help build safer, more transparent AI systems.

** 2. Measuring Dataset Quality**  
Not all data is good. Some datasets may be biased, low-quality, or too one-sided. But we still don’t have clear tools to measure whether a dataset is fair or harmful. This is an active area of research.

** 3. Searching Through Giant Datasets**  
Even if we know what to look for—like offensive language or false quotes—finding it in trillions of words is extremely hard. Tools like ROOTS are helping, but they’re early-stage and limited. Better search and filtering tools are urgently needed.

---

###  Connecting Data to Model Behavior

Sometimes, an AI behaves badly not because of a design flaw, but because of what it learned during training. This raises an important question: how do we connect what a model does to the data that shaped it?

Here are four major research areas in this space:

** 1. How Pretraining Shapes Behavior**  
Pretraining feeds huge amounts of data to a model. But we still don’t fully understand how specific examples affect what the model learns. For example:

- If a harmful phrase appears often, does the model copy it?  
- Can a small number of bad examples cause strange behavior?  

Researchers need better ways to link pretraining data to model outputs.

**🧪 2. Fine-Tuning and Its Effects**  
After pretraining, models are usually fine-tuned with extra data or human feedback. This helps them behave more safely. But it’s not clear how much this actually changes the model—or whether it removes or adds bias. Measuring the effect of fine-tuning is still an open problem.

** 3. The Role of Synthetic Data**  
Some developers use synthetic data—fake data generated by other models—to improve training. This can be helpful for privacy and balance, but raises new concerns:

- Does synthetic data make models too artificial?  
- Could it cause new types of mistakes?  

We need more research to understand how synthetic data affects fairness and accuracy.

** 4. Balancing Privacy and Accountability**  
To trace where a model learned something, we need good tracking tools. But there’s a trade-off:

- If we share too much, we risk exposing private or copyrighted data.  
- If we share too little, it’s hard to hold anyone accountable.  

Tools like TRAK are trying to solve this by helping track data sources without violating privacy. But it's still early days.

---

###  Wrapping Up

We often think of AI safety as something that happens *after* a model is built—but this paper shows it’s really a design problem from the start. If we want AI to be fair, safe, and trustworthy, we need better tools to check the data, test model behavior, and trace where things go wrong. That’s what Technical AI Governance is all about. And as AI keeps growing, this kind of behind-the-scenes work might turn out to be the most important part of all.

---

### 📚 Reference

Reuel, A., Bucknall, B., Casper, S., Fist, T., Soder, L., Aarne, O., Hammond, L., Ibrahim, L., Chan, A., Wills, P., ... Trager, R. (2024, July 20). Open problems in technical AI governance. Centre for the Governance of AI. https://www.governance.ai/research/open-problems-in-technical-ai-governance
