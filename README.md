# Taiwo Alabi

**I build AI systems that know when to say "I don't know."**

MSc Artificial Intelligence, National College of Ireland · Dublin

---

## Why that sentence, and not something about Python

Most AI systems have one setting: answer. Ask them anything and they produce something,
confidently, every time.

That is fine when the stakes are a film recommendation. It stops being fine when the system
is routing a customer complaint, checking whether a face belongs to the right person,
deciding how much money to risk, or telling a doctor about your medical history.

**Confident wrongness is the failure mode nobody catches**, because it does not look like a
failure. It looks like an answer.

So I keep building the other thing. Every project below has a moment where the system stops
and hands the decision back to a human, and in most of them that moment is the part I am
proudest of.

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

It was right, and it did not know it was right. That gap is the whole reason the confidence
gate exists.

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

`FastAPI` `PostgreSQL + pgvector` `Llama 3.1` `LangGraph` `Docker`

---

### 📜 [TermsGuard AI](https://github.com/iamtamilore/terms-guard-ai) · [try it live](https://newtazer-terms-guard-ai.hf.space)
*Reads the small print for you and warns you about the sneaky bits.*

Reading every privacy policy you accept in a year would take **244 hours**. So 91% of people
tick "I agree" and unknowingly consent to their data being sold. It is like signing a
contract in a language you do not speak, handed to you by the person who wrote it.

**87% F1**, and grounding the model in retrieved text cut invented content by **77%**.

**The bit I like:** the summary used to be written by a language model, and it hallucinated
GDPR article numbers. A wrong legal citation is worse than no citation, because it sounds
authoritative. So I deleted the clever version and replaced it with a boring template that
cannot make things up.

`Sentence-BERT` `FAISS` `Claude API` `Flask`

---

### 📈 [AI Trading Assistant](https://iamtamilore.github.io/ai-trading-assistant/)
*Reads 48 world markets each morning and gives one clear call on each.*

People do not usually lose money because they picked a bad company. They lose it because
they panicked, and sold at the bottom.

Four separate models vote, and at least two of three have to agree before anything happens.
Which is why on a normal day it says **wait** on about two thirds of everything.

**The bit I like:** tested across 2022, when the US market fell 20% and Bitcoin fell 65%,
it lost **1.2%**. Not because it predicted the crash. Because it had rules about when to
step back, and it followed them. Validated over **7,800 walk-forward windows** with no
data leakage.

Paper trading, not real money, and I say so on the page.

`PyTorch` `PatchTST` `SAC / TD3 / PPO` `Hidden Markov Models`

---

### 🏠 [Share-A-Home](https://shareahome.onrender.com)
*A live marketplace for students finding rooms and landlords filling the gaps between them.*

Deployed and running. Listings, ID verification, chat, viewing bookings, e-signed contracts,
ratings.

**The bit I like:** I was asked to add a "forgot password" page. The app is passwordless by
design, so instead of quietly reversing that decision I put the choice back to the user with
the reasoning: the magic link already *is* a one-time reset link. We kept it passwordless.
Every decision like that is written down in a numbered decision register, alongside a threat
model and a data governance doc.

`FastAPI` `Supabase PostgreSQL` `Render` `HTMX`

---

### 👁️ Campaign Image QA *(private until graded)*
*Catches the moment an AI-generated model stops being the same person.*

Generating campaign images for a fashion brand, I kept hitting the same problem: ask for
"the same model from the side" and the generator invents a *similar but different* person.
Fifty images per model, checked by eye, and human eyes get worse at this after twenty.

**F1 0.90, ROC-AUC 1.00, and zero false alarms.**

**The bit I like:** it detects off-style images **without ever having been shown a bad one**.
It only studies good images and learns to redraw them. When something off-brand arrives, the
redraw comes out wrong, and that error is the alarm. Which matters, because nobody has a
labelled library of "campaign photos that went wrong."

`TensorFlow` `ResNet50` `Siamese networks`

---

## Where this comes from

Four returning internships at **Huawei Technologies**, on a telecom billing platform carrying
**400 million call records a day**. My job was making data trustworthy enough that a manager
would act on it: cataloguing what every field meant, mapping it across 61 warehouse tables,
and writing 440+ test cases to prove it was right.

You do not spend four summers on data quality at that scale and then go on to build AI that
answers confidently regardless of whether it should.

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

Open to graduate and internship roles in Dublin, particularly anywhere the cost of a
confidently wrong answer is high: health, finance, regulated industries, AI evaluation and
safety.

[Email](mailto:alabitaiwo625@gmail.com) · [LinkedIn](https://www.linkedin.com/in/tami-alabi/)
