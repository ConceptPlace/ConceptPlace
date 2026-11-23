<div align="center">
  <img src="assets/Banner-conceptplace.PNG" alt="Concept Place — AI workspace for founders" width="100%">

  # Concept Place

  **Turn an idea into a clear, testable business plan.**

  [![Visit Concept Place](https://img.shields.io/badge/Visit-Concept_Place-6C5CE7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://www.conceptplace.in/)
  [![Early access](https://img.shields.io/badge/Status-Early_Access-F39C12?style=for-the-badge)](https://www.conceptplace.in/)
  [![Made in India](https://img.shields.io/badge/Made_in-India-138808?style=for-the-badge)](https://www.conceptplace.in/contact)

  <br>

  **Strategy · Content · Campaigns · Scenario Planning · Automation**
</div>

<br>

## About

**Concept Place** is an AI-powered business workspace built for founders who want to move from a raw idea to a focused next step.

Bring business chat, marketing strategy, editable content drafts, campaign calendars, financial scenario analysis, and workflow discovery into one connected workspace—so you can explore, test, create, and launch with greater clarity.

> Built by **Grow Millions Private Limited** in India.

---

## Product Preview

<div align="center">
  <img src="assets/Screenshot%202026-11-23%20182848.png" alt="Concept Place idea exploration preview" width="49%">
  <img src="assets/Screenshot%202026-11-23%20182913.png" alt="Concept Place workspace preview" width="49%">
</div>

---

## What You Can Do

| | Feature | Designed to help you |
|:---:|---|---|
| 🧠 | **MARK AI** | Ask business questions, reason through decisions, and continue with focused follow-ups. Use Normal mode for depth or Duo mode to compare trade-offs. |
| 📈 | **Marketing Strategist** | Shape an offer and audience into a practical marketing plan and campaign direction. |
| ✍️ | **Content Generator** | Create editable text and storyboard drafts for your campaigns. |
| 🗓️ | **Content Calendar** | Organize posts and filter campaign activity by date or platform. |
| 📢 | **Auto Post** | Prepare posts and schedules for supported connected social accounts, with human review before publication. |
| 🔮 | **Oasis Discovery** | Test pricing, costs, demand, and customer-acquisition assumptions through interactive business scenarios. |
| ⚙️ | **Automation Marketplace** | Discover ready-made workflows for follow-ups and everyday operations. |
| ✅ | **Compliance** | Track India-focused incorporation milestones and business tasks in one practical checklist. |

---

## Start in 7 Steps

1. **Visit** [conceptplace.in](https://www.conceptplace.in/) and start free—no card required.
2. **Tell MARK AI** what you are building, where you are today, and what decision you need to make.
3. **Create a strategy** for your audience, offer, positioning, and campaign direction.
4. **Generate content** that can be reviewed and adapted to your brand.
5. **Explore assumptions** in Oasis Discovery, including price, costs, demand, and acquisition cost.
6. **Organize the next move** in your Content Calendar or discover an automation.
7. **Experiment, learn, and refine** with a small real-world test.

<div align="center">

[![Explore MARK AI](https://img.shields.io/badge/Explore-MARK_AI-6C5CE7?style=flat-square)](https://www.conceptplace.in/mark-ai-new)
[![Marketing Strategist](https://img.shields.io/badge/Open-Marketing_Strategist-00A884?style=flat-square)](https://www.conceptplace.in/marketing-strategist)
[![Oasis Discovery](https://img.shields.io/badge/Try-Oasis_Discovery-F39C12?style=flat-square)](https://www.conceptplace.in/oasis-discovery)

</div>

---

## Platform Links

- [Start with MARK AI](https://www.conceptplace.in/mark-ai-new)
- [Open Marketing Strategist](https://www.conceptplace.in/marketing-strategist)
- [Explore Content Calendar](https://www.conceptplace.in/content-calendar)
- [Explore Auto Post](https://www.conceptplace.in/auto-post)
- [Discover Oasis](https://www.conceptplace.in/oasis-discovery)
- [Explore Automation Marketplace](https://www.conceptplace.in/automation-market-place)
- [Explore Compliance](https://www.conceptplace.in/compliance)
- [Contact Grow Millions](https://www.conceptplace.in/contact)

---

## Important Notes

> 💡 **Scenario results are exploration tools, not guaranteed forecasts.** Outcomes depend on the assumptions you enter.

- Social publishing availability depends on platform permissions, account type, and supported formats.
- Content should be reviewed, fact-checked, and adapted to your audience.
- Financial, legal, tax, and compliance decisions should be checked with qualified professionals.
- Product capabilities evolve through phased releases and early-access feedback.

---

## Developer Backend

This repository contains the serverless backend source for MARK AI workflows.

### Technology

<div align="center">

![AWS SAM](https://img.shields.io/badge/AWS-SAM-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-FF9900?style=for-the-badge&logo=awslambda&logoColor=white)
![API Gateway](https://img.shields.io/badge/AWS-API_Gateway-FF4F00?style=for-the-badge&logo=amazonapigateway&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

</div>

| Path | Purpose |
|---|---|
| `hello_world/` | Lambda function source code |
| `events/` | Sample invocation events |
| `tests/` | Unit and integration tests |
| `template.yaml` | AWS SAM infrastructure template |

### Requirements

- AWS SAM CLI
- Python 3
- Docker
- Configured AWS credentials

### Build and Deploy

```bash
sam build --use-container
sam deploy --guided
```

### Test Locally

```bash
sam local invoke HelloWorldFunction --event events/event.json
sam local start-api
curl http://localhost:3000/
python -m pytest tests/unit -v
```

See the [AWS SAM Developer Guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html) for deployment documentation.

---

<div align="center">

### Built for founders who want to test, learn, and launch with clarity.

[Visit Concept Place](https://www.conceptplace.in/) · [Contact Us](https://www.conceptplace.in/contact)

</div>
