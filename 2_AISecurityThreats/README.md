# TryHackMe - AI Security Threats

**Platform**: TryHackMe  
**Difficulty**: Easy  
**Category**: AI Security  
**Date**: 10 OCT 2026  
**Time spent**: ~1 hour (including write-up)  
**Tags**: `#AI` `#MachineLearning` `#PromptEngineering` `#MITREATLAS` `#DefensiveAI` `#DataPoisoning` `#ISO27090` `#TryHackMe`

---

## Summary

This is an entry-level room covering the fundamental building blocks of Artificial Intelligence and Machine Learning. You explore foundational ML mechanics, neural architectures, and how modern Large Language Models (LLMs) operate and consume structured data.

## Key Takeaways

- **Pattern recognition and syntax match are critical**: LLMs do not "think" like humans; they track probabilistic weightings and structural cues. Adhering closely to expected formatting prevents prompt drifting and hallucinations.
- **Learn model-friendly markup**: Structuring prompts and classification inputs using standardized encoding—such as clean Markdown headers, delimiter tags (`###`, `---`), or schemas like JSON/YAML—significantly improves model parsing reliability, token boundary comprehension, and response accuracy.

---

## AI Agents

Each agent has a specific operational workflow:

- Target IP / hostname
- AI Agent interaction
- Natural language interface that adapts and presents escalating resistance through each tier
- 7 tasks in total

---

## Learning Objectives & Tasks

### Task 1 – Intro
Sets up what you will learn and focus on, it encourages you to remember what you have learned so far. Pay attention to key words and vocabulary. It sets the objectives.

### Task 2 – Vulnerabilities in AI Models
We will learn about these Vulnerabilities through the MITRE ATT&CK framework, but using the AI focus, ATLAS framework. The Vulnerabilities are broken down to five groups.
	I. Propmt Injection - This is when you enter an input into the chatbot that bypasses instructions, restrictions, or overrides set instructions placed on the chatbot. It causes it to reveal information that was outside of its defined scope.
	II. Data Poisoning - manipulating the data or text that the AI is trainied on so that it causes defects in its training. This occurs before training. 
	III. Model Theft - Unauthorized access to AI models, either steal in whole or use it for illicit purposes. One method is accessing it through the API and use the output to train another or replicate it.
	IV. Privacy Leakage - When the data it was trained on gets leaked even though it is private information. Usually sensitive data that it was trained on.
	V. Model Drift - This is when a model falls behind based on old training. It loses the ability to perform work properly.
You will now prepare to use these Vulnerabilities to attack a fictional AI assistant. Use Prompt Injection. MENTOR will be the agent you attack. Hint: Treat it like a child that you are trying to train.

### Task 3 – AI-Enhanced Attacks
The current attacks are still the same as have been used over the years, the difference is they are quicker and more enhanced with AI-tools. 
- **AI-Generated Malware** Instead of being required to know how to do things to create attackware now AI can do it for you. It has made users more effective. Here are some of the AI-Generated Malware:
	I. Deepfakes - Generated AI that convinces people to belive something or someone because it has training data on a specific person. It can be in the form of Voice, video, emails, anything that is used to communicate.
	II. AI-Enhanced Phishing - emails used to get a person to perform an action that will compromise a system. They used to be identifiable by bad grammar, spelling and other oddities. Attackers can not use AI to make it more believable and fluent. LLM's are not supposed to make malicious contact by default but as previously seen Prompt Injections can break the rules in AI.
You are to identify the types of attacks. Some are from this lesson the last is hinted in the beginning when you think of any kind of current attack. So knowing other forms of attack will be need to be understood.

### Task 4 – Defensive AI
Harness the Power. Ai is powerful and a good attack tool, but it is also a powerful defensive tool. Those using it for defensive purposes are shown to decrease the average cost of breach because they were able to identify and contain breaches faster, by 108 days. Four areas AI has had a defensive impact.
	I. Analysis - helps in security work because it does well at pattern recognition.
	II. Prediciton - By knowing historical info and understanding how AI is used in better phishing, it is able to reverse or understand that and be more aware.
	III. Summarization - It can dissect copious amount of data and logs that are generated from attacks. It is able to draw correlations that a human might miss.
	IV. Investigation - It can go through raw data and run reports for a human to evaluate. It can also help with threat hunting by looking at things that humans might miss.
The AEGIS chatbot sample is a complete Walkthrough, just perform the tasks it asks.

### Task 5 – Securing AI
The New Frontier. Using AI for advanced cyber security is the correct answer, the reports clearly show this. However, if you adopt AI in your system, you need to secure it properly or it will add to your attack surface.

**AI Security Hygiene**
- Securing AI Models - Learn RBAC and MFA.
- Privacy Protection - sensitive data: audit, minimize and encrypt
- AI Security Standards - learn ISO/IEC 27090
- Model Monitoring - Tools to know: SHAP and LIME.

### Task 6 – Practical
Time to go to work. Graduation Time - 
Modern generative LLMs are scaled transformer architectures that predict token sequences based on learned multi-dimensional patterns. Answer the questions.

### Task 7 – Conclusion
Key points
- Artificial Intelligence - broad field 
- Machine Learning - Subfield of AI
- Nueral Networks - replicates the human brain. More than three layers is Deep Learning
- Large Language Modles - subfield of AI built on Nueral Networks
- Vulnerabilities, Propmt Injection, data poisoning, model theft, privacy leakage, and model drift. Mapped by MITRE ATLAS framework.
- Attackers use AI in current attack models. Making it faster and cheaper.
- Defenders use AI to analyze, predict, summarize and investigate. IBM Data shows saving when using AI to enhance defense.
- AI adoption needs to be secured. learn ISO/IEC 27090 and ongoing model monitoring.

### Summary
I've learned that implementing AI in security has helped save cost in security breaches. However, securing the the AI is important otherwise you are increasing your attack surface. There is a MITRE ATLAS (Adversarial Threat Landscape for Artifical-Intelligence Systems) that is use for AI cybersecuirty. The security guidance to know is the ISO/IEC 27090 for AI cybersecurity risks.
# TryHackMe - AI Security Threats

**Platform**: TryHackMe  
**Difficulty**: Easy  
**Category**: AI Security  
**Date**: 11 OCT 2026  
**Time spent**: ~1 hour (including write-up)  
**Tags**: `#AI` `#MachineLearning` `#PromptEngineering`

---

## Summary

This is an entry-level room covering the fundamental building blocks of Artificial Intelligence and Machine Learning. You explore foundational ML mechanics, neural architectures, and how modern Large Language Models (LLMs) operate and consume structured data.

## Key Takeaways

- **Pattern recognition and syntax match are critical**: LLMs do not "think" like humans; they track probabilistic weightings and structural cues. Adhering closely to expected formatting prevents prompt drifting and hallucinations.
- **Learn model-friendly markup**: Structuring prompts and classification inputs using standardized encoding—such as clean Markdown headers, delimiter tags (`###`, `---`), or schemas like JSON/YAML—significantly improves model parsing reliability, token boundary comprehension, and response accuracy.

---

## AI Agents

Each agent has a specific operational workflow:

- Target IP / hostname
- AI Agent interaction
- Natural language interface that adapts and presents escalating resistance through each tier
- 7 tasks in total

---

## Learning Objectives & Tasks

### Task 1 – Intro
Sets up what you will learn and focus on, it encourages you to remember what you have learned so far. Pay attention to key words and vocabulary. It sets the objectives.

### Task 2 – Vulnerabilities in AI Models
We will learn about these Vulnerabilities through the MITRE ATT&CK framework, but using the AI focus, ATLAS framework. The Vulnerabilities are broken down to five groups.
I. Propmt Injection - This is when you enter an input into the chatbot that bypasses instructions, restrictions, or overrides set instructions placed on the chatbot. It causes it to reveal information that was outside of its defined scope.
II. Data Poisoning - manipulating the data or text that the AI is trainied on so that it causes defects in its training. This occurs before training. 
III. Model Theft - Unauthorized access to AI models, either steal in whole or use it for illicit purposes. One method is accessing it through the API and use the output to train another or replicate it.
IV. Privacy Leakage - When the data it was trained on gets leaked even though it is private information. Usually sensitive data that it was trained on.
V. Model Drift - This is when a model falls behind based on old training. It loses the ability to perform work properly.
You will now prepare to use these Vulnerabilities to attack a fictional AI assistant. Use Prompt Injection. MENTOR will be the agent you attack. Hint: Treat it like a child that you are trying to train.

### Task 3 – AI-Enhanced Attacks
The current attacks are still the same as have been used over the years, the difference is they are quicker and more enhanced with AI-tools. 
- **AI-Generated Malware** Instead of being required to know how to do things to create attackware now AI can do it for you. It has made users more effective. Here are some of the AI-Generated Malware:
I. Deepfakes - Generated AI that convinces people to belive something or someone because it has training data on a specific person. It can be in the form of Voice, video, emails, anything that is used to communicate.
II. AI-Enhanced Phishing - emails used to get a person to perform an action that will compromise a system. They used to be identifiable by bad grammar, spelling and other oddities. Attackers can not use AI to make it more believable and fluent. LLM's are not supposed to make malicious contact by default but as previously seen Prompt Injections can break the rules in AI.
You are to identify the types of attacks. Some are from this lesson the last is hinted in the beginning when you think of any kind of current attack. So knowing other forms of attack will be need to be understood.

### Task 4 – Defensive AI
Harness the Power. Ai is powerful and a good attack tool, but it is also a powerful defensive tool. Those using it for defensive purposes are shown to decrease the average cost of breach because they were able to identify and contain breaches faster, by 108 days. Four areas AI has had a defensive impact.
I. Analysis - helps in security work because it does well at pattern recognition.
II. Prediciton - By knowing historical info and understanding how AI is used in better phishing, it is able to reverse or understand that and be more aware.
III. Summarization - It can dissect copious amount of data and logs that are generated from attacks. It is able to draw correlations that a human might miss.
IV. Investigation - It can go through raw data and run reports for a human to evaluate. It can also help with threat hunting by looking at things that humans might miss.
The AEGIS chatbot sample is a complete Walkthrough, just perform the tasks it asks.

### Task 5 – Securing AI
The New Frontier. Using AI for advanced cyber security is the correct answer, the reports clearly show this. However, if you adopt AI in your system, you need to secure it properly or it will add to your attack surface.

**AI Security Hygiene**
- Securing AI Models - Learn RBAC and MFA.
- Privacy Protection - sensitive data: audit, minimize and encrypt
- AI Security Standards - learn ISO/IEC 27090
- Model Monitoring - Tools to know: SHAP and LIME.

### Task 6 – Practical
Time to go to work. Graduation Time - 
Modern generative LLMs are scaled transformer architectures that predict token sequences based on learned multi-dimensional patterns. Answer the questions.

### Task 7 – Conclusion
Key points
- Artificial Intelligence - broad field 
- Machine Learning - Subfield of AI
- Nueral Networks - replicates the human brain. More than three layers is Deep Learning
- Large Language Modles - subfield of AI built on Nueral Networks
- Vulnerabilities, Propmt Injection, data poisoning, model theft, privacy leakage, and model drift. Mapped by MITRE ATLAS framework.
- Attackers use AI in current attack models. Making it faster and cheaper.
- Defenders use AI to analyze, predict, summarize and investigate. IBM Data shows saving when using AI to enhance defense.
- AI adoption needs to be secured. learn ISO/IEC 27090 and ongoing model monitoring.

### Summary
I've learned that implementing AI in security has helped save cost in security breaches. However, securing the the AI is important otherwise you are increasing your attack surface. There is a MITRE ATLAS (Adversarial Threat Landscape for Artifical-Intelligence Systems) that is use for AI cybersecuirty. The security guidance to know is the ISO/IEC 27090 for AI cybersecurity risks. Better to use it than get left behind.

