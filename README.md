# Taiwo Alabi

**I tune AI to the cost of being wrong.**

MSc Artificial Intelligence, National College of Ireland · Dublin

**[iamtamilore.github.io](https://iamtamilore.github.io)** · every project below has a full write-up there, with the diagrams, plots and results.

---

## Why that sentence, and not something about Python

Every model has a dial on it. Turn it one way and it flags too much, and people stop
trusting the system. Turn it the other way and it misses the thing that mattered.

**There is no setting that is simply correct.** Where the dial goes depends on what it
costs when the system is wrong, and that cost is different in every product. Getting it
right in one project tells you almost nothing about the next one.

So that is the question I start from. Not *how accurate is it*, but **what happens when
it's wrong, and which kind of wrong is worse?**

Four projects below, five different answers. One of them has no dial at all, and that is
the one I would point at first.

---

## The projects

### 🤖 [Customer Care Process Automation](https://github.com/iamtamilore/customer-care-automation)
*Two robots that took over two jobs I used to do by hand every morning.*

I had a job sorting hundreds of customer complaints before 9am. So I replaced it: one
rule-following bot for the fussy checking, one AI agent for reading complaints and deciding
which team they belong to. **95.2% accuracy.**

**The bit I like:** I gave the agent five complaints it had never seen. It got all five
right, and still flagged two for a human, because those two only scored 0.37 and 0.41
confidence.

It was right, and it was not sure. Those are different things.

**Cost of being wrong:** a misroute costs a customer days of waiting. A needless escalation
costs an agent five minutes. Wildly lopsided, so I set the dial to escalate freely.

`Python` `scikit-learn` `BPMN 2.0`

---

### 🏥 [Smart Medical Records Engine](https://github.com/iamtamilore/agentic_rag_fastapi)
*Helps a doctor find the one thing in your file that matters, before your appointment ends.*

Your doctor has ten minutes. Somewhere in three years of notes is a line saying you reacted
badly to a medicine. They are about to prescribe you something.

This lets them just ask, in normal English, and get the answer out of **your own file**.

**The bit I like:** the search filters to your patient ID *before* it ranks by similarity,
not after. Skip that and a search will cheerfully return a different patient's note because
it happens to be worded the same way. Same illness, same phrasing, wrong human. Cross-patient
leakage is not something you catch in review, it is something you design out.

The whole thing runs on the hospital's own machine. Nothing goes to anyone's cloud.

**Cost of being wrong:** a data breach, and possibly a wrong prescription. Too expensive to
leave to a threshold-so this is the project with **no dial in it at all**. The failure is
designed out at the query, not tuned down afterwards. Knowing when not to use a threshold
is the part I had to learn.

`FastAPI` `PostgreSQL + pgvector` `Llama 3.1` `LangGraph` `Docker`

---

### 📜 [TermsGuard AI](https://github.com/iamtamilore/terms-guard-ai) · [try it live](https://newtazer-terms-guard-ai.hf.space)
*Reads the small print for you and warns you about the sneaky bits.*

Nobody reads privacy policies. It is like signing a contract in a language you do not speak,
handed to you by the person who wrote it. Reading every one you would actually encounter in a
year would take **244 hours**, so **91%** of people just tick "I agree" and unknowingly consent
to their data being sold.

**The bit I like:** the summary used to be written by a language model, and it hallucinated
GDPR article numbers. A wrong legal citation is worse than no citation, because it sounds
authoritative. So I deleted the clever version and replaced it with a boring template that
cannot make things up. Grounding the model in retrieved text instead of letting it
free-associate cut invented content by **77%**, and it holds **87% F1** doing it.

**Cost of being wrong:** telling you your bank's terms are predatory when they are not. A
bad warning is worse than no warning, so anything under the confidence line is not shown at
all-not shown with a caveat.

`Sentence-BERT` `FAISS` `Claude API` 

### 👁️ Campaign Image QA *(private until graded)*
*Catches the moment an AI-generated model stops being the same person.*

Generating campaign images for a fashion brand, I kept hitting the same problem: ask for
"the same model from the side" and the generator invents a *similar but different* person.
Fifty images per model, checked by eye, and human eyes get worse at this after twenty.

**F1 0.90, ROC-AUC 1.00, and zero false alarms.**

**The bit I like:** it detects off-style images **without ever having been shown a bad one**.
It only studies good images and learns to redraw them. When something off-brand arrives, the
redraw comes out wrong, and that error is the alarm. This matters, because nobody has a
labeled library of "campaign photos that went wrong."

**Cost of being wrong:** here it is the false alarm, not the miss. A quality gate that cries
wolf gets switched off within a week. So zero false positives was the target, not a bonus.

`TensorFlow` `ResNet50` `Siamese networks`

---

## Where this comes from

Four returning internships at **Huawei Technologies**, on a telecom billing platform carrying
**400 million call records a day**. My job was making data trustworthy enough that a manager
would act on it: cataloguing what every field meant, mapping it across 61 warehouse tables,
and writing 440+ test cases to prove it was right.

That is where the habit comes from. At that volume, the cost of a wrong
number is a manager acting on it, so you learn to ask what a mistake actually costs before
you decide how careful to be.

I also spent three months as an **AI Quality Analyst evaluating Google Gemini** - reading
model outputs and documenting precisely where and how they slipped. Same instinct, from the
other side.

---

## What I work with

**Languages** Python, SQL
**ML** scikit-learn, TensorFlow/Keras, PyTorch, transfer learning, reinforcement learning
**AI systems** RAG, LangChain/LangGraph, vector search (pgvector, FAISS), LLM evaluation
**Data** PostgreSQL, HDFS, HBase, GaussDB
**Deploy** Docker, Docker Compose, Kubernetes, FastAPI, Flask
**Governance** GDPR cataloguing, data lineage, EU AI Act, UAT test design

---

## Get in touch

Open to graduate and internship roles in Dublin, particularly where being wrong is
expensive: health, finance, regulated industries, AI evaluation and safety.

[Email](mailto:alabitaiwo625@gmail.com) · [LinkedIn](https://www.linkedin.com/in/tami-alabi/)
