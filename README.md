# LLM Powered Debugger for Pippy

<p align = "center">
    <img src="public/assets/c4gt_DMP.png" height="200px"/>
    <img src="public/assets/logoOpt.png" height="200px" />
</p>

## Contributor Details

**Name:** Harshit Verma  
**Email:** [therealharshit014@gmail.com](therealharshit014@gmail.com)  
**GitHub:** [therealharshit](https://github.com/therealharshit)   
**Blogs** [Harshit Verma](https://www.sugarlabs.org/authors/harshit-verma)  
**Organization:** [Sugar Labs](https://www.sugarlabs.org/)  
**Project:** [LLM-powered Debugger for Pippy](https://github.com/sugarlabs/Pippy/issues/95)  
**Mentors:** [Walter Bender](https://github.com/walterbender), [Ibiam Chihurumnaya](https://github.com/chimosky), [Kshitij Shah](https://github.com/kshitijdshah99)  


## Introduction  

Debugging is one of the most challenging parts of programming for beginners, especially children who are just starting their coding journey. While many Large Language Models (LLMs) are marketed as tools that “write code for you,” they also have great potential to guide learners through the process of **understanding and fixing errors** in their code.  

The **Pippy Debugger** project was developed to harness this potential by integrating an **LLM-powered debugger** into the Pippy Activity which is a Python learning environment in Sugar. The goal was not just to provide solutions, but to **teach children how to debug**, giving them context, explanations, and guidance in an age-appropriate manner.  


## Objectives  

- To integrate an **LLM-powered debugger** within the Pippy Activity.  
- To make debugging **accessible, engaging, and educational** for children.  
- To provide **contextual feedback** that helps learners understand the purpose of their code before debugging.  
- To ensure **seamless integration with Sugar AI**, allowing Pippy to use centralized inference endpoints.  
- To design a system where **debugging history is saved to the Journal**, enabling reflection and learning over time.  


## Background  

Many debugging tools are built for professional developers and are often too complex for beginners. Existing LLM applications primarily focus on code generation, while their educational potential for debugging remains underexplored.  

The proposed Pippy Debugger builds on the idea of **guiding learners through a debugging journey** rather than spoon-feeding solutions. By integrating with Pippy and Sugar AI:  
- Learners see the **context of their code** before debugging starts.  .  
- The output is filtered and **age-appropriate** for children.  

## Methodology  

### Tools & Technologies Used  
- **FastAPI** – for building the backend `/debug` endpoint.  
- **Sugar AI** – centralized inference system powering the debugger.  
- **LLMs** – primarily **Mistral 7B** and later **Gemma-3-27B-IT** for improved responses.  
- **GTK 3** – for UI integration in Pippy.  
- **LangChain** – to chain multiple LLM calls for better prompt workflows.  
- **Markdown Parsing** – custom parser to display responses clearly in the debugging terminal.  

### Workflow  
1. Learner writes Python code in **Pippy**.  
2. On clicking **Debug**, the code is sent to the `/debug` endpoint in **Sugar AI**.  
3. The backend processes the request, retrieves model inference, and formats the response.  
4. The response is contextualized, simplified, and displayed in a **debugging terminal** inside Pippy.  
5. **Debug history** (code, errors, suggestions) is saved into the Journal for future reflection.  

## Technical Implimentation

### **Phase 1 (Week 1 – Week 3): Exploration & Setup**
- Studied the **Pippy codebase** and its integration with Sugar.  
- Explored **Sugar AI** and tested existing endpoints.  
- Evaluated multiple **LLM options** (CodeLlama, Mistral via Ollama).  
- Mentor suggested moving inference to **Hugging Face models**.  
- Improved **base prompt design** for debugging tips.  
- Experimented with different ways of displaying debugging responses.  

---

### **Phase 2 (Week 4 – Week 6): Backend Development & UI Integration**
- Set up a **FastAPI server** with a `/debug` endpoint.  
- Integrated **Mistral 7B** model through Hugging Face for debugging.  
- Added **Run** and **Debug** buttons in the Pippy UI.  
- Built a **debugging terminal** in GTK.  
- Implemented **contextualization** – showing learners the **code context** before debugging starts.  
- Raised a **PR in Sugar AI** for `/debug` endpoint.
- Learned **LangChain** for chaining LLM calls into a structured workflow.  

---

### **Phase 3 (Week 7 – Week 9): Refinement & Sugar AI Integration**
- Prepared and presented **midterm PPT** for DMP evaluation.  
- Continued developing and refining the `/debug` endpoint in **Sugar AI**.  
- Completed integration of `/debug` endpoint.  
- Tested debugging responses on various buggy Python codes.  
- Found that some responses were too technical → began **refining prompt workflow**.  

---

### **Phase 4 (Week 10 – Week 12): Optimization**    
- Shifted to a larger model (**Gemma-3-27B-IT**) for more age-appropriate responses.  
- Improved **prompt workflows** to simplify explanations for children.  
- Enhanced Markdown parser for better formatting in the debugging terminal.  
- Began work on **saving debug history** to the Sugar Journal.  
- Designed a **JSON-based structure** for storing session details (code, error, AI suggestions).  
- Partially implemented prototype for saving and retrieving debug logs.  

## Demonstrations

### UI Implimentation 

- Updated Pippy UI:  
  ![Pippy UI](public/assets/Pippy-UI01.png)  

- Debugging terminal with LLM response:  
  1. ![Debug Terminal](public/assets/Pippy-UI02.png)  

  2. ![Debug Terminal](public/assets/Pippy-UI03.png)  


### Video  
[Watch Demo](https://drive.google.com/file/d/1zOzEthdjRFpUnj-tRhF7dghteNTd7-Bs/view?usp=sharing)  

## Resources

### Code Repositories  
- [Pippy Debugger Backend](https://github.com/sugarlabs/pippy-debugger-backend)  
- [Sugar AI](https://github.com/sugarlabs/sugar-ai)  
- [Pippy](https://github.com/sugarlabs/Pippy)  

### Pull Requests  
- [Sugar AI: Add /debug endpoint for Pippy Debugger #28](https://github.com/sugarlabs/sugar-ai/pull/28)  
- [Pippy: Pippy Debugger Integration #113](https://github.com/sugarlabs/Pippy/pull/113)

### Docs
- [Responses from the Debugger](https://docs.google.com/document/d/1zy0udbisHH9ZMHo3ln6tbKVYhPTRfw4cs9N0g3W_CKg/edit?usp=sharing)  

## Conclusion  

The Pippy Debugger successfully laid the foundation for an **AI-powered debugging assistant** tailored for children. With the ability to display contextual explanations, simplify errors, and guide learners through debugging, the project moves one step closer to making programming education more accessible and engaging.  

## Acknowledgment  

This project was completed under the mentorship of **Walter Bender**, **Ibiam Chihurumnaya** & **Kshitij Shah** as part the **Dedicated Mentorship Program 2025**.

I sincerely thank my **mentors**, the **Sugar Labs**, and **C4GT** community for their continuous guidance and support throughout this project.

It has been an incredibly rewarding summer working on this project, where I not only had the opportunity to contribute to open-source development but also to learn, grow, and collaborate with an inspiring community. This experience has motivated me to carry forward the spirit of open source, to continue contributing, and to build tools and software that make technology more accessible and impactful for everyone.

---
