---
title: "Event 2"
date: 2026-05-23
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# EVENT REPORT "FCAJ COMMUNITY DAY - AI, CLOUD AND ENTERPRISE SYSTEMS"

### Event Video

```text
https://www.youtube.com/watch?v=XjMCrcDRACQ
```

### Purpose of the Event

**FCAJ Community Day** was a community sharing event for students and learners who are interested in AWS, Cloud, AI, DevOps, Software Engineering, and modern product development.

The event did not only focus on technical knowledge. It also shared real-world experience from enterprise environments, production systems, hackathons, AI adoption, security, compliance, and career development in the AI era.

The main purposes of the event included:

- Helping participants understand how AI is changing the job market.
- Sharing what students and freshers need to prepare to compete in the modern IT market.
- Introducing how to use AI effectively through context, prompt, AI mindset, and AI adoption.
- Presenting practical AI use cases such as Amazon Q, agents, dashboards, meeting summarization, and workflow automation.
- Explaining Amazon CloudFront in terms of CDN, pricing, security, cost optimization, and high availability.
- Sharing a real 36-hour hackathon experience and how to build a usable product under time pressure.
- Explaining why Large Language Models may still produce different outputs even when temperature is set to 0.
- Introducing how to design an enterprise-grade multi-agent system for a real business use case.
- Emphasizing the importance of security, compliance, audit trails, guardrails, and product mindset in enterprise systems.

### List of Speakers / Presenters

Based on the transcript, the event included several sharing sessions from different speakers:

- **Quynh Mai**: The host of the event, introducing the spirit of connection and community sharing.
- **Nguyen Gia Hung**: AWS Solution Architect at AWS Vietnam and founder of FCAJ, sharing about the job market, AI, and how students should prepare for the future.
- **Tinh / Thinh**: Platform Engineer at Gotam X, sharing about context, prompt, AI mindset, AI adoption, and how to use AI tools more effectively.
- **Hai Anh**: Sharing about Amazon Q, agents, business intelligence, dashboard creation, automation, and meeting summarization.
- **Nguyen Han Thinh**: DevOps Engineer, sharing in-depth knowledge about Amazon CloudFront, flat-rate pricing, security, cost optimization, and performance.
- **UTM Morpho Team**: Sharing the journey of joining a 36-hour hackathon, forming an idea, building a product, and lessons learned.
- **LLM Determinism Speaker**: Sharing about temperature, token generation, inference optimization, and why LLM output may still vary even when temperature is 0.
- **Enterprise Multi-Agent System Speaker**: Sharing how to design an enterprise-grade multi-agent system for startup credit assessment.

---

## 1. Opening Session - The Job Market and the Impact of AI

### Main Content

The opening session was shared by **Nguyen Gia Hung**, AWS Solution Architect at AWS Vietnam and founder of FCAJ.

He began by asking participants about the current IT job market. Many students and freshers feel that the market has become more difficult, especially because AI is becoming stronger. However, he provided a different perspective: when a technology makes software development cheaper and more efficient, the demand for software does not decrease. Instead, it can increase significantly.

He used the example of **LED lights**. When LED lights made lighting much cheaper than traditional bulbs, people did not use less lighting. Instead, lighting demand increased dramatically, from homes and staircases to gardens and cities at night.

Similarly, when AI makes software development cheaper and faster, the number of software products created in the future may increase significantly.

### AI Does Not Remove All Jobs, But It Changes the Type of Jobs

One important message was that AI may make software creation easier, but it also creates new types of work.

In the past, many people had ideas but did not have enough money to hire a technical team to build a product. Today, thanks to AI, even people outside IT such as lawyers, doctors, or business users can create MVPs or prototypes.

However, when more products are created, new needs also appear:

- Fixing AI-generated products.
- Maintaining MVPs that are not production-ready.
- Scaling systems when they have real users.
- Operating, securing, and optimizing systems.
- Building platforms and infrastructure so products can run reliably.
- Turning demos into real products that enterprises can use.

Therefore, instead of only worrying that AI will replace developers, learners should understand that AI is changing the requirements of the job market.

### Why Is the Current Period Difficult?

Nguyen Gia Hung explained that the current period is a transition stage. Large companies are investing heavily in AI infrastructure, AI hardware, and AI models. At the same time, they need to optimize costs, which creates short-term impacts on employment.

However, in the long term, the demand for software and software-related work is still likely to increase.

For Vietnam, he mentioned that the IT industry has long been known for **outsourcing**. Many international organizations open technical hubs in Vietnam because of the talent pool. Therefore, students should not only look at the local market. They need to prepare themselves to compete in the global market.

### What Students Need to Prepare

He emphasized that a university degree or basic technical knowledge is no longer enough.

Students and freshers need to prepare:

- A strong technical foundation.
- Practical knowledge about the industry they want to work in.
- Understanding of real enterprise use cases.
- Real products instead of only demos.
- Soft skills, English, networking, and personal branding.
- The ability to explain what value they can bring to an organization.

For example, if someone wants to become an AI Engineer in banking, they should not only show exercises such as license plate detection or shelf detection. Instead, they should understand what problems banks have, what systems they use, what use cases are valuable, and how AI can contribute to the business.

### Product Is More Important Than Demo

A clear message from this session was:

```text
The current market needs real products, not only demos.
```

In the past, students could show small projects or simple demos. But in the AI era, when even non-IT people can create products, software engineers need to prove that they can create something that can be deployed, operated, maintained, and scaled.

A good product should show:

- A clear user or use case.
- A reasonable architecture.
- Deployment capability.
- Operational readiness.
- Monitoring.
- Security.
- Documentation.
- Scalability.

### Lessons Learned

- AI does not only reduce jobs; it also creates new software needs and new types of work.
- Students need to prepare more than technical knowledge.
- Real products are more valuable than simple demos.
- Business knowledge and industry use cases are important advantages.
- Learners should not delay learning and building projects because the market changes very fast.

---

## 2. Session 1 - Context, Prompt and AI Mindset

### Topic Introduction

The next session was shared by **Tinh / Thinh**, Platform Engineer at Gotam X.

The main topic was how to use AI more effectively, especially by providing the right **context**. He did not go too deeply into one specific technology because participants had different backgrounds such as development, backend, frontend, UI/UX, DevOps, and students.

Instead, he chose an open topic that everyone could apply to their own background.

### What Is a Platform Engineer?

He briefly explained the role of a **Platform Engineer**.

In the past, when developers wanted to deploy an application, they often had to ask DevOps to provision databases, servers, infrastructure, or other resources. If a company has hundreds of developers, handling every request manually becomes very time-consuming.

A Platform Engineer builds an internal platform that allows developers to provision resources by themselves, while still staying within the standards and controls of the platform team. In other words, Platform Engineering turns infrastructure into a self-service platform with governance.

### The Problem of Using AI Without Context

A common mistake when using ChatGPT or AI tools is using one single chat for too many different purposes.

For example, in one conversation, a user may ask about:

- A travel plan to Hoi An.
- CV review.
- Recruitment advice.
- Coding.
- AWS knowledge.
- Career questions.

When the context changes too often, AI can become confused because it does not know exactly what the user is doing. This is similar to asking a person too many unrelated topics in one conversation.

Therefore, when working with AI, users need to provide the correct context for each task.

### What Is Context?

Context means the background information or environment of a task. AI has a large amount of general knowledge, but to answer correctly for a specific situation, the user must provide relevant information.

A good context may include:

- The user’s goal.
- The role that AI should play.
- Who the user is.
- What project the user is working on.
- Rules or standards of the company or team.
- Code style or project conventions.
- Related documents.
- Expected output.

For example, if the user is new to AWS, they should say:

```text
I am new to AWS. Please explain this concept in a simple way with easy examples.
```

Then AI can explain more clearly and in more detail than if the user only says "explain this."

### Do Not Provide Too Much Unnecessary Information

Another important point is that context does not mean giving as much information as possible.

If users provide too much information that AI already knows, or too many unrelated documents, the context becomes diluted. This can make the answer less accurate.

The speaker called this behavior **Internet Puller**, which means pulling everything from the Internet because it looks useful.

Examples include:

- Copying too many code review rules from the Internet.
- Adding too many AI plugins.
- Using many prompt frameworks without understanding them.
- Providing too many unrelated documents.
- As a result, AI follows the wrong rules or gives answers that do not fit the project.

Therefore, context must be filtered carefully:

```text
Correct context is better than too much context.
```

### AI First Mindset and AI Adoption

The speaker suggested two important keywords for learners to research:

- **AI First Mindset**
- **AI Adoption**

AI First Mindset means treating AI as a regular supporting tool in work, but not using AI blindly. Users need to know when to use AI, why to use it, and how to evaluate the result.

AI Adoption is the process of organizations applying AI to their workflow, products, and operations. Learners should understand this trend because large companies are increasingly evaluating whether candidates can use AI properly.

### Second Brain and AI Context

The speaker also mentioned the concept of **Second Brain**.

Second Brain is a way to organize notes, documents, knowledge, and personal experience into a system that can be retrieved later. When combined with AI, it can provide higher-quality context.

For example, instead of explaining the whole project again every time, a user can prepare:

- Project documentation.
- Code rules.
- System architecture.
- Team conventions.
- Previous technical decisions.
- Learning notes.

This allows AI to understand the user better and provide more accurate support.

### Confidence in Sharing and Asking Questions

Another important topic was confidence. The speaker mentioned that in interviews, many candidates have knowledge but do not dare to speak, answer in English, or share their thoughts.

This reduces their opportunity, especially when the fresher and intern market is highly competitive.

Learners should practice:

- Confidently sharing ideas.
- Speaking even when they are not perfect.
- Asking questions when they do not know something.
- Presenting their thinking process.
- Improving communication and presentation skills.

### Lessons Learned

- AI needs the right context to answer accurately.
- One chat should not be used for too many unrelated topics.
- Do not copy too many rules, plugins, or prompts from the Internet without understanding them.
- Context should focus on what is specific to the project, team, or company.
- AI First Mindset and AI Adoption are important trends to learn.
- Second Brain can help manage knowledge and provide better AI context.
- Learners need to practice confidence in sharing, asking questions, and interviewing.

---

## 3. Session 2 - Amazon Q, Agents and Workflow Automation

### Topic Introduction

The next session was presented by **Hai Anh**. He shared about Amazon Q and how AI agents can support users in office tasks, data analysis, and workflow automation.

He began by sharing his personal experience presenting at international events such as Singapore and Silicon Valley. The message was that young people can create opportunities if they have confidence, real products, and the ability to solve real problems for users.

### Real-World Problem

In enterprises, many people such as managers, seniors, directors, or CEOs spend a lot of time collecting data, creating weekly reports, reading Excel files, analyzing numbers, summarizing meetings, or sending next steps to related stakeholders.

These tasks are usually:

- Repetitive.
- Time-consuming.
- Not always requiring deep technical skills.
- Slowing down decision-making.
- Taking time away from more important work.

Amazon Q was introduced as a friendly AI assistant that can connect data sources and automate part of this workflow.

### What Is an Agent?

The speaker explained agents in a simple way.

A normal Large Language Model is like a brain that can reason and respond. However, if it only has a brain, it cannot take actions such as scheduling meetings, sending emails, retrieving data, or updating systems.

An agent combines:

- An LLM brain.
- Tools or actions.
- Connections to external services.
- A workflow to perform tasks.

An agent can be understood as an LLM with "extended arms" that can work with Gmail, Calendar, Microsoft Teams, Confluence, Jira, Microsoft Cloud, or other systems.

### Amazon Q and Agent Platform

Amazon Q was presented as a platform that allows users to create agents based on their own needs.

Some mentioned capabilities included:

- Connecting with Microsoft tools such as PowerPoint, Word, and Teams.
- Connecting with Google tools such as Gmail and Calendar.
- Creating data dashboards.
- Chatting directly with data.
- Automating workflows.
- Creating meeting summarization agents.
- Sending next steps to related people through email.
- Helping non-BI users analyze data.

### Dashboard Demo From an Excel File

In the demo, the speaker described a case where a user uploads an Excel file containing data such as sale orders, revenue, or quarterly performance.

Previously, a BI user might need tools such as Microsoft BI or OpenSearch to build dashboards. With Amazon Q, users can upload an Excel file and ask AI to create a dashboard or analyze the data.

Example:

```text
Analyze this sale order data and create an overview dashboard.
```

Then the system can generate visual analysis and allow the user to ask follow-up questions in natural language.

### Meeting Summarization Demo

The speaker also demonstrated another flow: creating an agent to summarize a meeting.

The agent can be configured with the role:

```text
Meeting summarization assistant
```

Its tasks include:

- Receiving transcript or meeting data.
- Summarizing the overview.
- Listing decisions.
- Listing action items.
- Identifying next steps.
- Sending emails or integrating with Microsoft Teams if connected.

In the demo, because the machine was not connected to email or Microsoft Teams, the speaker focused on the meeting summarization part.

### Integration With MCP

The speaker also mentioned MCP as a way to extend the ability of LLMs or agents.

MCP can be understood as a mechanism that helps agents connect with external tools, systems, or actions. Thanks to MCP, agents do not only respond with text, but can also call tools, process data, and execute workflows.

### Lessons Learned

- AI agents do not only answer questions; they can also perform actions.
- Amazon Q can support data analysis, dashboard creation, and workflow automation.
- Non-BI users can interact with data using natural language.
- Meeting summarization and action item extraction are practical enterprise use cases.
- Agents need integrations with systems such as email, calendar, Teams, or MCP to create real value.
- When building agents, security, permissions, and enterprise data must be considered carefully.

---

## 4. Session 3 - Amazon CloudFront: Pricing, Security, Cost Optimization and Performance

### Topic Introduction

The next session was presented by **Nguyen Han Thinh**, DevOps Engineer, about **Amazon CloudFront**.

Amazon CloudFront is usually known as a CDN service from AWS, but the speaker emphasized that CloudFront is not only a CDN. It is also a platform for optimizing performance, protecting applications, and controlling cost.

### Problem With Pay-As-You-Go

Previously, when using CloudFront with the pay-as-you-go model, users paid based on actual usage. This is beneficial when traffic is low because the cost can be very small. However, it also makes cost prediction difficult.

A major problem happens when traffic increases unexpectedly, for example:

- The website is attacked by DDoS.
- The website suddenly becomes viral.
- Bots send many requests.
- Data transfer out increases sharply.

In these cases, CDN costs can spike unexpectedly and create serious risks for individuals, startups, or small businesses.

### CloudFront Flat-Rate Pricing

The speaker introduced the new **flat-rate pricing** mechanism of CloudFront.

Instead of only using pay-as-you-go, AWS provides fixed plans such as:

- Free.
- Pro.
- Business.
- Premium.

Users can choose a plan based on their needs. If the usage exceeds the plan, the system may become slower or bandwidth may be limited, but there will be no unexpected extra charges like in the pay-as-you-go model.

This solves one of the biggest concerns for businesses:

```text
Not being able to predict the bill at the end of the month.
```

### CloudFront User Groups

AWS divides users into different groups.

#### Small Website Owners

This group includes personal websites, small blogs, small startups, or learning projects. They need basic performance improvement and protection with low cost.

#### Business Users

This group needs stronger protection, better control, private origin, and better security features for enterprise environments.

#### Mid-size / Large Enterprises

This group needs lower latency, higher usage limits, origin failover, log reduction, high availability, and advanced security.

### CloudFront Network Infrastructure

CloudFront runs on AWS global edge locations and points of presence. These locations connect to nearby ISPs so that user requests can reach the system faster.

AWS also has its own backbone network, which helps data move between regions and origins with high speed and reliability.

When network issues happen, such as cable failures or routing problems, AWS can reroute traffic so that users can still access the application without noticing the issue.

### Protection Against DDoS and Volumetric Attacks

CloudFront helps protect systems from distributed attacks by blocking traffic closer to the attack source.

If bots from a certain country send traffic to a website, the requests pass through a nearby edge location and can be blocked there instead of reaching the origin server.

This helps protect the origin from overload.

CloudFront supports mechanisms such as:

- Distributed defense.
- SYN proxy to prevent SYN flood.
- Attack visibility dashboard.
- 24/7 security support for higher-tier plans.

### Cost Optimization With CloudFront

The speaker gave an example of a WordPress website hosted on EC2 with around 150 GB of data transfer out per day.

Without CloudFront, origins such as EC2 or ALB must handle more requests, which increases data transfer cost, LCU usage, and system load.

With CloudFront:

- Content is cached.
- Fewer requests reach the origin.
- ALB load is reduced.
- Direct data transfer from origin is reduced.
- EC2 CPU usage is reduced.
- Overall operational cost can be reduced.

### Content Compression

CloudFront supports **content compression**, which compresses content before sending it to users.

By enabling content compression in distribution behavior, CloudFront can reduce the amount of data transferred.

This helps:

- The website load faster.
- Reduce data transfer.
- Reduce cost.
- Improve user experience.

### Security With CloudFront

CloudFront supports HTTPS through integration with AWS Certificate Manager. Users can create a TLS certificate and configure HTTPS easily.

AWS also uses its own security library such as **s2n** to optimize TLS handshakes and reduce latency.

CloudFront also supports **mutual TLS (mTLS)**. With mTLS, both the client and server need certificates to authenticate each other. This feature is suitable for high-security systems such as financial systems, exclusive game distribution, or internal APIs.

### Origin Protection

CloudFront helps hide the origin and reduce direct access to the origin server.

Some ways to protect the origin include:

- Using VPC Origin to connect CloudFront with an origin inside a private subnet.
- Using S3 Block Public Access.
- Allowing only CloudFront to access S3 or the origin.
- Restricting security groups by CloudFront IP ranges.
- Adding custom headers to verify requests from CloudFront.
- Using geo restriction to block or allow traffic by country.
- Using signed URLs or signed cookies to protect private content.

### Reliability and Performance

CloudFront supports **origin failover**. If the primary origin fails, CloudFront can redirect requests to a backup origin to keep the website available.

CloudFront also supports custom error pages to improve user experience when errors occur.

For performance, CloudFront uses multi-layer caching:

```text
Viewer
  ↓
Point of Presence
  ↓
Regional Edge Cache
  ↓
Origin
```

If there are 10,000 requests, CloudFront can reduce the number of requests sent to the origin, preventing the origin server from being overloaded.

### HTTP/3 and TCP Optimization

CloudFront supports HTTP/3 with multiplexing, which allows multiple requests to be processed concurrently and reduces page load time.

CloudFront can also reuse TCP connections at the edge location, reducing repeated handshakes and improving response speed.

### CloudFront Functions

CloudFront Functions allow lightweight logic to run at edge locations.

Some use cases include:

- Redirecting users by country.
- Rewriting URLs.
- Redirecting users based on mobile or desktop devices.
- Handling headers.
- Optimizing routing before requests reach the origin.

### Lessons Learned

- CloudFront is not only a CDN; it also supports security, performance, and cost optimization.
- Flat-rate pricing reduces the risk of unexpected billing spikes.
- CloudFront reduces load on the origin and lowers data transfer cost.
- Content compression, caching, HTTP/3, and edge functions improve performance.
- VPC Origin, signed URLs, geo restriction, and mTLS improve security.
- Origin failover and custom error pages improve system reliability.

---

## 5. Session 4 - The 36-Hour Hackathon Journey With UTM Morpho

### Topic Introduction

The next session was shared by the **UTM Morpho** team about their journey in a 36-hour hackathon.

The name **UTM** came from the first letters of the three team members, while **Morpho** carried the meaning of something new and fresh. This reflected the team’s spirit of creating something new and useful for real work.

### Why the Team Joined the Hackathon

The team learned about the competition from a colleague. The format was that teams had 36 continuous hours to build a usable product and present it to the judges.

The team joined because they wanted to:

- Challenge themselves under time pressure.
- See what they could build in 36 hours.
- Connect with experts in IT and AI.
- Experience working like a mini startup.
- Create a real product instead of only an idea.

### Idea Formation Process

At first, the team had many brainstorming sessions but could not find an idea good enough. After the opening session, judging criteria, and timeline were announced, the team decided to go back and think calmly.

Instead of looking for a very large or abstract idea, they looked at their daily work. They noticed that many people use AI to generate UI, but whenever they want to change a button color, spacing, layout, or component, they need to prompt again.

This creates several problems:

- It takes time.
- It consumes tokens.
- Small details are hard to edit.
- AI may regenerate the whole UI in an unexpected way.
- Users cannot directly interact with the generated interface.

From this, the team came up with an idea to build an app that allows users to:

- Generate UI from input.
- Choose templates.
- Upload images or draw a simple layout.
- Render UI into HTML.
- Edit directly on the interface.
- Drag and drop components.
- View source code.
- Save edit history.
- Publish a link for others to review.

### Project Architecture

The project used a simple serverless architecture. The most important part was the AI pipeline.

The pipeline included three main agents.

#### Agent 1 - Vision Analysis

This agent receives user input, especially images or sketches. It analyzes the image, detects layout, components, and UI structure, then returns a JSON layer.

#### Agent 2 - Code / Layout Engine

The second agent reads the JSON data from Agent 1, then generates size, CSS, layout, and UI structure information.

#### Agent 3 - Design Agent

The third agent is configured with a design-focused system prompt. It reads the requirements from Agent 2 and generates HTML/CSS interface code for the user.

### Product Demo

In the demo, the team showed a user interface with a left-side panel where users can enter their requirements.

Users can:

- Choose templates.
- Upload images.
- Use the camera.
- Draw simple layouts.
- Generate dashboards or UI.
- View HTML source code.
- Drag and drop components directly on the interface.
- Edit elements manually.
- View edit history.
- Publish an HTML link to share with friends or colleagues for review.

The feature the team was most proud of was **direct editing on the generated UI**. Users do not need to prompt again from the beginning just to edit a small element.

### Challenges During the Hackathon

The team faced many difficulties.

#### Token Limit

While building the product, the AI tool hit the token limit and the team had to wait around two hours. This interrupted progress because the agent was still in the middle of a task, and the team did not want to switch to a different agent.

#### AI Over-Generation

Sometimes, the team gave a simple requirement, but AI interpreted it too broadly and generated too much unnecessary code. The team had to control the output to prevent the code from becoming too large and difficult to fix.

#### Time Pressure

The team spent around 12 hours thinking about the idea, so they only had about 24 hours left to build the product. Near pitching time, they had to prepare the demo video, slides, presentation script, and product at the same time.

#### Physical Fatigue

The hackathon lasted 36 continuous hours. Around 4 or 5 a.m., everyone was tired, but the workload increased. The team had to manage their energy to finish the product and present it well.

### Lessons Learned

The team learned several important lessons.

#### The Idea Does Not Need to Be Too Big

Instead of choosing a very large or abstract problem, the team chose a small problem that they actually faced every day. This made the product practical and easier to explain.

#### More Features Do Not Always Mean Better

At first, the team wanted to add many features. However, because time was limited, they had to focus on the most important feature: direct UI editing experience.

#### Teamwork Is Very Important

Because the members had worked together before and understood each other's strengths, they could divide tasks faster, collaborate better, and merge everything into a complete product.

#### Health Management Is Part of a Hackathon

In a 36-hour hackathon, eating, drinking, resting, and managing energy are important so that the team can still pitch well at the end.

### Lessons Learned From This Session

- Hackathons help train the ability to build products under time pressure.
- Good ideas can come from small daily work problems.
- Teams should focus on core features instead of adding too many features.
- AI is useful, but token limits, output control, and scope management are important.
- Teamwork, task division, and communication strongly affect the final result.
- People should not hesitate to join hackathons because they are great opportunities to learn quickly.

---

## 6. Session 5 - Why LLMs Are Not Fully Deterministic Even When Temperature Is 0

### Topic Introduction

The next session discussed a more technical topic: how Large Language Models generate output and why the output may still change even when **temperature = 0**.

The speaker emphasized that an LLM is a **probabilistic engine**. The generated tokens are always influenced by probability, even when users try to reduce randomness.

### How LLMs Work

An LLM works by selecting the next most suitable token to complete a response.

A simplified process is:

1. The user sends a prompt.
2. The model scores all tokens in its vocabulary.
3. Tokens are ranked based on their scores.
4. The model selects the next token.
5. The process repeats until the response is complete.

The score of each token is usually called a **logit**.

### What Is Temperature?

Temperature is a parameter that controls model randomness.

- Higher temperature: more creative and random output.
- Lower temperature: more stable output.
- Temperature = 0: in theory, the model always selects the highest-scoring token.

When temperature is greater than 0, the model uses softmax to select tokens based on probability distribution. When temperature is 0, the model uses greedy decoding, which means it always chooses the highest-scoring token.

### Common Assumption

Many people assume that:

```text
Temperature = 0 → Same prompt → Always same output
```

This is important in production workflows because many systems want LLM outputs to behave like traditional deterministic workflows.

However, reality is not always that simple.

### Why Can Output Still Be Different?

The speaker explained two main reasons.

#### Technical Reason

Computers do not process floating-point numbers perfectly. When GPUs perform parallel computation, the order of addition, rounding, and floating-point operations can differ between runs.

For example:

```text
(a + b) + c
```

and

```text
a + (b + c)
```

may produce tiny differences when using floating-point arithmetic.

When there are millions or billions of calculations, these small differences can accumulate and affect token scores.

#### Inference Optimization by Providers

A larger reason comes from hosting providers such as OpenAI, Anthropic, or Amazon Bedrock. To reduce cost and improve performance, providers may apply inference optimization techniques.

One common technique is batching: combining many short prompts into one larger batch so that the GPU can process them together.

As a result, even if the user sends the same prompt, the actual GPU processing environment may be different between runs. This can make output vary even when temperature is 0.

### Bedrock and Local Model Demo

The speaker demonstrated the same prompt with temperature = 0.

Example prompt:

```text
Write me a story about the great polar bear in Antarctica.
```

When running on Bedrock, two runs could generate different outputs in terms of token count and content.

When running the same model locally with the same temperature = 0 setting, the outputs were almost exactly the same.

This showed that provider-side inference optimization can affect determinism.

### Impact on Production

This is important because some use cases require stable and predictable outputs.

Examples include:

- Automated workflows.
- Document processing.
- Data extraction.
- Text classification.
- JSON generation for downstream services.
- Financial or legal applications.
- Critical systems requiring audit.

If downstream services assume that the output is always in the correct format, the system may fail when the LLM returns a different format.

### Mitigation Strategies

The speaker suggested several mitigation strategies.

#### Run Multiple Times and Select the Common Answer

A system can run multiple agents or multiple generations, then use another agent to select the most consistent answer.

This can improve accuracy, but it increases:

- Cost.
- Latency.
- Architecture complexity.

#### Self-Host the Model

If absolute control is required, a team can self-host the model on its own infrastructure. This allows control over runtime, inference stack, and configuration.

However, this increases operational cost and loses some benefits from provider economies of scale.

#### Use Format-Supporting Parameters

Some providers offer features such as JSON mode. When JSON mode is enabled, the model is more likely to return valid JSON instead of unnecessary explanations.

This helps downstream systems process output more reliably.

#### Design Downstream Services to Handle Errors

Most importantly, teams should not assume that LLM output is always perfect. Downstream services must handle multiple cases:

- Wrong output format.
- Missing fields.
- Extra unwanted text.
- Different outputs between runs.
- Hallucination.

### Model Configuration Notes

The speaker also mentioned that in some cases, temperature = 0 may make the model repeat words or sentences. In those cases, temperature around 0.1 can keep the output stable while reducing repetition.

If self-hosting a model, repeat penalty can be used, but it must be used carefully because it can negatively affect code or JSON generation.

The most important point is:

```text
Always read the official documentation of the model before configuring it.
```

### Lessons Learned

- LLMs are probabilistic models, not deterministic workflows.
- Temperature = 0 does not guarantee identical output 100% of the time.
- Provider inference optimization can change output.
- If stable output is required, mitigation strategies are necessary.
- Downstream services must be able to handle imperfect outputs.
- Testing is critical when using LLMs in production.

---

## 7. Session 6 - Enterprise-Grade Multi-Agent System for Startup Credit Assessment

### Topic Introduction

The final session focused on how to build an **enterprise-grade multi-agent system** for startup credit assessment.

The speaker emphasized that after many technical sessions, this section would shift toward business mindset: how to design a system that has real users, solves a real problem, and can be used in an enterprise environment.

Four important questions were introduced:

```text
Who will use it?
What will they use?
Why should they use it?
When is the right time to use it?
```

### Business Problem

In banking, assessing credit for startups is more difficult than assessing traditional enterprises.

Startups often do not have the factors that traditional credit models require:

- No 3-year financial statements.
- No clear credit history.
- No large collateral assets.
- Short operating history.
- Main assets are ideas, intellectual property, founders, and traction.
- Important data exists across many dimensions such as market, team, revenue, user growth, product, and public social presence.

At the same time, startups are an important business segment because Vietnam is encouraging innovation and entrepreneurship.

### Why GenAI Is Needed

Startup data often does not fit traditional credit models. Therefore, GenAI can help collect, analyze, and summarize different data dimensions.

Some possible dimensions include:

- Financial data.
- Market data.
- Founder profile.
- Team background.
- Traction.
- TAM / SAM / SOM.
- Competitor landscape.
- Growth potential.
- Risk factors.

TAM, SAM, and SOM were explained as:

- **TAM**: Total Addressable Market.
- **SAM**: Serviceable Available Market.
- **SOM**: Serviceable Obtainable Market.

### Single Agent or Multi-Agent?

The speaker asked whether startup credit assessment should use a single agent or a multi-agent system.

The answer was multi-agent, because the problem involves many data types and requires different types of expertise.

A single agent is suitable for:

- Simple POCs.
- Single-domain tasks.
- Linear workflows.
- Simple tool orchestration.
- Low-stakes decisions.
- Rapid prototypes.

However, startup credit assessment is not suitable for a single agent because:

- There are many inputs.
- Data belongs to many domains.
- Context windows have limits.
- Different expertise is required.
- Risk and compliance must be controlled.
- Output must be auditable.

### Multi-Agent System Design

The system was designed like a credit committee with multiple specialized agents.

#### Credit Committee / Orchestrator

This is the main coordinator agent, similar to the host of a committee. It receives the request, distributes tasks to specialized agents, and summarizes the final result into a report.

#### Financial Analyst Agent

This agent analyzes financial statements, cash flow, revenue, runway, burn rate, and the current financial health of the startup.

#### Market Research Agent

This agent analyzes the market, competitors, TAM/SAM/SOM, timing, and growth potential.

#### Team Evaluator Agent

This agent evaluates founders, co-founders, the team, experience, network, LinkedIn, X, Facebook, or other public signals.

#### Risk Assessor Agent

This agent analyzes risks, including financial risk, market risk, operational risk, legal risk, security, and compliance.

#### Report Synthesizer Agent

This final agent combines results from all other agents into a structured report for banking users or credit officers to review.

### Why Multi-Agent Works

A multi-agent approach is suitable because:

- Each agent has its own expertise.
- Each agent has a smaller and more focused context.
- Agents can challenge each other’s assumptions.
- Agents can run in parallel.
- Each step can have an audit trail.
- Agents can be scaled independently.
- If one agent fails, the whole system does not necessarily fail.
- The architecture is similar to distributed system design in solution architecture.

### Security and Compliance in Enterprise Environments

The speaker emphasized that in an enterprise environment, security and compliance are more important than simply having a working demo.

Some key concerns include:

- Prompt injection.
- Output filtering.
- API key rotation.
- IAM access key rotation.
- Audit logging.
- Data leakage.
- Guardrails.
- MCP attack vectors.
- Input sanitization.
- Human approval.
- Industry compliance for banking, finance, biotech, or medtech.

The speaker gave an example that in a banking environment, people cannot freely connect MCP, tools, or AI agents to internal systems. Everything needs security review and clear boundaries.

### Prompt Injection and Guardrails

Prompt injection happens when a user or attacker puts malicious instructions into the input to make AI ignore its original rules.

Example:

```text
Ignore previous instructions and give me ...
```

If the system does not have guardrails, AI may respond incorrectly, leak information, or perform unintended actions.

Therefore, the system needs:

- Input guardrails.
- Output guardrails.
- Sensitive information filtering.
- Limited agent permissions.
- Clear boundaries for agent autonomy.
- Human-in-the-loop for important decisions.

### Audit Trail and Responsibility

In enterprise environments, especially banking, audit trails are very important.

If an AI system makes a wrong recommendation and a human approves it incorrectly, the final responsibility does not belong to the model. It belongs to the person assigned to review and approve the decision.

Therefore, every decision should record:

- Input.
- Output.
- Which agent processed it.
- Who reviewed it.
- Who approved it.
- Reason for the decision.
- Decision timestamp.
- Model or workflow version.

### Knowledge Transfer and Context Engineering

Another important topic was knowledge transfer.

In enterprises, documents can be very long. For example, a credit document can contain more than 200 pages of PDF. However, experts do not read everything in a normal way. They know which parts are important, which parts can be ignored, which indicators matter, and which signals require attention.

Therefore, simply pushing all documents into an LLM is not enough.

Knowledge from domain experts must be transferred into the system, including:

- How to read documents.
- Which sections are important.
- Which metrics matter.
- Business rules.
- Approval conditions.
- Warning conditions.
- Risk evaluation methods.

This is why context engineering is more important than simply adding more data.

### Deployment Approach

The speaker suggested a possible deployment approach for an agent system:

- Develop locally.
- Containerize the application.
- Push the image to ECR.
- Use an agent runtime / Bedrock Agent Core or similar platform to deploy.
- Create an endpoint.
- Connect Lambda or API Gateway.
- Build the frontend with React, Streamlit, or another framework.
- Call API Gateway to interact with the agent system.

### ROI and Business Value

When bringing a solution into an enterprise, it is not enough to say "the code is done." The team must prove value using numbers.

Some questions to answer include:

- How much time did the process take before the system?
- How many hours are saved after the system?
- How much cost is reduced?
- How much productivity is improved?
- How much risk is reduced?
- What is the payback period?
- What is the ROI?

The speaker emphasized:

```text
Numbers speak louder than words.
```

### Suggestions for Students / Freshers

The speaker suggested that learners can turn this idea into an end-to-end project for their CV.

Possible components include:

- Frontend.
- AWS Cognito for authentication.
- JWT understanding.
- Backend.
- Agent permission design.
- Controlled MCP integration.
- Infrastructure as Code using Terraform.
- AWS deployment.
- Security, audit trail, and logging.
- A system that can serve real users.

The speaker also emphasized that backend and software engineering knowledge are still very important. AI is a strong advantage, but it does not replace engineering fundamentals.

### Final Message

The final message of the session was:

```text
Building a system is not only about making it run.
It must run safely, reliably, and serve users.
```

### Lessons Learned

- System design should start from users and business problems.
- Multi-agent systems are suitable for multi-domain and expertise-heavy problems.
- Enterprise AI systems need security, compliance, audit trails, and guardrails.
- AI should not be fully autonomous in critical decisions.
- Knowledge transfer and context engineering are very important.
- A CV project should have an end-to-end flow, not only a demo.
- Terraform and Infrastructure as Code are useful skills to learn.
- AI is powerful, but backend, software engineering, and system design remain the foundation.

---

## What I Learned After the Event

### About the Job Market

After the event, I understood that AI does not simply remove developer jobs. AI makes software creation cheaper, which may increase the number of software products. However, the requirements for software engineers also become higher.

Learners do not only need to know how to code. They also need to know how to:

- Build real products.
- Understand business domains.
- Understand enterprise use cases.
- Operate systems.
- Understand security and monitoring.
- Explain the value they create.

### About Using AI

I learned that AI needs the right context. If the context is wrong or diluted, AI may answer incorrectly or fail to meet the real need.

A good prompt is not just a long prompt. It must contain the important information that matches the task.

I also learned several important concepts:

- AI First Mindset.
- AI Adoption.
- Second Brain.
- Context Engineering.
- Prompt Injection.
- Guardrails.
- MCP attack vector.

### About AWS and Cloud

The event helped me understand more deeply about many AWS services and cloud concepts, such as:

- Amazon Q.
- Amazon CloudFront.
- Amazon S3.
- Amazon Cognito.
- Amazon API Gateway.
- AWS Lambda.
- Amazon Bedrock.
- Amazon DynamoDB.
- Amazon CloudWatch.
- AWS Certificate Manager.
- Terraform and Infrastructure as Code.

In particular, the CloudFront session helped me understand that a CDN is not only used for caching content. It can also help reduce cost, protect origins, prevent DDoS, improve performance, and increase reliability.

### About AI in Production

I learned that putting AI into production is not just about calling a model API. Teams must care about:

- Output is not fully deterministic.
- Temperature = 0 does not guarantee identical output.
- Providers may use inference optimization.
- Downstream services must handle invalid outputs.
- Many test cases are needed.
- Guardrails, logging, and audit trails are important.

### About Product Building

From the hackathon session, I learned that a good product does not always need to start from a huge idea. Sometimes, solving a small but real problem from daily work can create more practical value.

I also learned that under limited time, a team should focus on the core feature instead of trying to add too many features.

---

## Application to My Personal Project

After this event, I can apply many lessons to my **AWS Serverless E-commerce Platform** project.

### Applying Product Mindset

Instead of treating the e-commerce project as a simple demo, I should develop it like a real product.

The project should have:

- Clear user flow.
- Clear admin flow.
- Payment flow.
- Order management.
- Image upload.
- Authentication.
- Monitoring.
- Alerts.
- CI/CD.
- Security.
- Documentation.

### Applying CloudFront Knowledge

In my e-commerce project, CloudFront is used to distribute the frontend and product images. After the CloudFront session, I understand that CloudFront can also help:

- Speed up the website.
- Reduce requests to the S3 origin.
- Protect the origin bucket.
- Enable HTTPS.
- Use custom error pages.
- Optimize caching.
- Use signed URLs if private files need protection.
- Work with WAF to improve security.

### Applying Monitoring and Security

From the enterprise and production sharing sessions, I need to pay more attention to:

- CloudWatch Logs.
- CloudWatch Metrics.
- SNS alerts.
- IAM least privilege.
- Cognito authentication.
- API Gateway authorization.
- Audit logs for admin actions.
- Payment callback protection.
- Avoiding exposed access keys or secrets.

### Applying AI and Prompt Engineering

When using AI to support coding or documentation, I will:

- Separate chats by task.
- Provide the correct context.
- Avoid copying rules or prompts from the Internet without understanding them.
- Review AI output carefully.
- Test code before adding it to the project.
- Avoid letting AI make final decisions completely on its own.

### Applying Enterprise Multi-Agent Thinking

In the future, if I extend my e-commerce project, I can try building small agents to support:

- Order analysis.
- Revenue summarization.
- Best-selling product suggestions.
- Suspicious order detection.
- Product description generation for admins.
- Operation reports.

However, these agents must have guardrails, logging, and human review.

---

## Experience From Joining / Watching the Event

The event gave me many practical perspectives about AWS, AI, and the IT career path.

### Diverse Content

The sessions covered many different topics:

- The IT job market.
- AI mindset and prompt context.
- Amazon Q and agent automation.
- Amazon CloudFront.
- Hackathon and AI product building.
- LLM determinism.
- Enterprise multi-agent systems.

This helped me understand that technology is not only about code. It is also related to products, cost, security, operations, users, and business value.

### High Practical Value

Many sessions came from real enterprise experience, such as:

- Security review in banking.
- Difficulties when using AI in production.
- CloudFront cost concerns.
- A 36-hour hackathon experience.
- Responsibility when approving AI output.
- ROI mindset when presenting solutions to leadership.

These topics helped me understand the difference between a learning project and a production system.

### More Motivation to Learn AWS and AI

After the event, I gained more motivation to continue improving my AWS Serverless E-commerce Platform project. I realized that if I can combine AWS, AI, security, monitoring, and product mindset, my personal project can become a strong portfolio.

---

## Some Images From the Event

<img src="/workshop-/images/4-Events/event2.1.jpg" alt="FCAJ Community Day Event 2 Image 1" style="max-width: 100%; height: auto;">

<img src="/workshop-/images/4-Events/event1.2.jpg" alt="FCAJ Community Day Event 2 Image 2" style="max-width: 100%; height: auto;">

---

## Conclusion

Overall, **FCAJ Community Day - AI, Cloud and Enterprise Systems** was a very useful event for IT students, freshers, and people who are learning AWS or AI.

The event helped me understand that in the AI era, learners need more than coding skills. They need a strong technical foundation, product mindset, business understanding, the ability to use AI properly, cloud knowledge, security awareness, and the ability to build systems that can operate in real environments.

The most important lessons I learned were:

- AI changes the job market but also creates new opportunities.
- Learners need real products instead of only demos.
- Using AI effectively requires correct context, not just long prompts.
- Amazon Q and agents can support many practical enterprise workflows.
- CloudFront is not only a CDN; it also helps optimize cost, security, and performance.
- Hackathons train the ability to build products quickly and focus on core features.
- LLMs still have uncertainty even when temperature is 0.
- AI systems in production need testing, guardrails, and downstream error handling.
- Enterprise multi-agent systems must be designed with safety, audit trails, and business value.
- Building a system is not only about making it run. It must run safely, reliably, and serve users.

After the event, I have clearer direction to continue improving my **AWS Serverless E-commerce Platform** project and to learn more deeply about AWS, AI, CloudFront, Prompt Engineering, Security, Monitoring, Infrastructure as Code, and Enterprise System Design.
