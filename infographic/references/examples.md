# Infographic Examples Reference

Complete examples for all template categories.

---

## List Templates

### list-grid-badge-card — KPI Cards
```infographic
infographic list-grid-badge-card
data
  title Key Metrics
  desc Annual performance overview
  items
    - label Total Revenue
      desc $12.8M | YoY +23.5%
      icon mdi/currency-usd
    - label New Customers
      desc 3,280 | YoY +45%
      icon mdi/account-plus
    - label Satisfaction
      desc 94.6% | Industry leading
      icon mdi/emoticon-happy
    - label Market Share
      desc 18.5% | Rank #2
      icon mdi/trophy
```

### list-column-done-list — Checklist
```infographic
infographic list-column-done-list
data
  title Launch Checklist
  items
    - label Code review completed
      done true
    - label Tests passing
      done true
    - label Documentation updated
      done false
    - label Deploy to production
      done false
```

### list-row-horizontal-icon-arrow — Process Row
```infographic
infographic list-row-horizontal-icon-arrow
data
  title Development Process
  items
    - label Plan
      desc Define requirements
      icon mdi/clipboard-text
    - label Design
      desc Create wireframes
      icon mdi/pencil-ruler
    - label Build
      desc Write code
      icon mdi/code-tags
    - label Test
      desc Quality assurance
      icon mdi/test-tube
    - label Deploy
      desc Go live
      icon mdi/rocket-launch
```

### list-grid-candy-card-lite — Colorful Cards
```infographic
infographic list-grid-candy-card-lite
data
  title Our Services
  items
    - label Consulting
      desc Strategic business advice
    - label Development
      desc Custom software solutions
    - label Training
      desc Skill development programs
    - label Support
      desc 24/7 technical assistance
```

---

## Sequence Templates

### sequence-timeline-simple — Timeline
```infographic
infographic sequence-timeline-simple
data
  title Company History
  items
    - label 2020
      desc Company founded in Silicon Valley
    - label 2021
      desc Series A funding $5M
    - label 2022
      desc Expanded to 50 employees
    - label 2023
      desc Launched flagship product
    - label 2024
      desc IPO and global expansion
```

### sequence-roadmap-vertical-simple — Roadmap
```infographic
infographic sequence-roadmap-vertical-simple
data
  title 2024 Product Roadmap
  items
    - label Q1 2024
      desc Mobile app launch
      icon mdi/cellphone
    - label Q2 2024
      desc API v2.0 release
      icon mdi/api
    - label Q3 2024
      desc AI integration
      icon mdi/brain
    - label Q4 2024
      desc Enterprise features
      icon mdi/domain
```

### sequence-filter-mesh-simple — Funnel
```infographic
infographic sequence-filter-mesh-simple
data
  title Sales Funnel
  items
    - label Website Visitors
      value 100000
      desc Total traffic
    - label Leads
      value 25000
      desc 25% conversion
    - label Qualified
      value 5000
      desc 20% qualified
    - label Proposals
      value 1500
      desc 30% engaged
    - label Customers
      value 500
      desc 33% closed
```

### sequence-snake-steps-simple — Snake Steps
```infographic
infographic sequence-snake-steps-simple
data
  title Onboarding Process
  items
    - label Sign Up
      desc Create your account
    - label Verify Email
      desc Confirm your identity
    - label Complete Profile
      desc Add your information
    - label Connect Apps
      desc Integrate your tools
    - label Start Using
      desc Begin your journey
```

### sequence-stairs-front-compact-card — Stairs
```infographic
infographic sequence-stairs-front-compact-card
data
  title Career Growth Path
  items
    - label Junior
      desc Entry level position
    - label Mid-Level
      desc 2-3 years experience
    - label Senior
      desc Technical leadership
    - label Lead
      desc Team management
    - label Director
      desc Department oversight
```

### sequence-pyramid-simple — Pyramid
```infographic
infographic sequence-pyramid-simple
data
  title Maslow's Hierarchy
  items
    - label Self-Actualization
      desc Achieving full potential
    - label Esteem
      desc Recognition and respect
    - label Love/Belonging
      desc Relationships and community
    - label Safety
      desc Security and stability
    - label Physiological
      desc Basic survival needs
```

### sequence-circular-simple — Circular Flow
```infographic
infographic sequence-circular-simple
data
  title Agile Cycle
  items
    - label Plan
      desc Sprint planning
    - label Design
      desc Solution architecture
    - label Develop
      desc Implementation
    - label Test
      desc Quality assurance
    - label Review
      desc Retrospective
```

---

## Compare Templates

### compare-binary-horizontal-underline-text-vs — A vs B
```infographic
infographic compare-binary-horizontal-underline-text-vs
data
  title Cloud vs On-Premise
  items
    - label Cloud Solution
      children
        - label Scalability
          desc Scale on demand
        - label Cost
          desc Pay as you go
        - label Maintenance
          desc Provider managed
        - label Access
          desc Anywhere, anytime
    - label On-Premise
      children
        - label Control
          desc Full data ownership
        - label Cost
          desc One-time investment
        - label Maintenance
          desc Internal IT team
        - label Access
          desc Network dependent
```

### compare-swot — SWOT Analysis
```infographic
infographic compare-swot
data
  title Strategic Analysis 2024
  items
    - label Strengths
      children
        - label Strong R&D team
          desc 50+ engineers
        - label Patent portfolio
          desc 20+ patents
        - label Brand recognition
          desc Top 10 in industry
    - label Weaknesses
      children
        - label Limited budget
          desc Constrained resources
        - label Small sales team
          desc 5 representatives
        - label Legacy systems
          desc Technical debt
    - label Opportunities
      children
        - label AI market growth
          desc 40% CAGR
        - label New markets
          desc Asia expansion
        - label Partnerships
          desc Strategic alliances
    - label Threats
      children
        - label Competition
          desc Big tech entering
        - label Regulation
          desc New compliance rules
        - label Economy
          desc Recession risk
```

### compare-binary-horizontal-badge-card-arrow — Badge Comparison
```infographic
infographic compare-binary-horizontal-badge-card-arrow
data
  title Free vs Premium
  items
    - label Free Plan
      children
        - label 5 Projects
        - label 1 GB Storage
        - label Email Support
        - label Basic Analytics
    - label Premium Plan
      children
        - label Unlimited Projects
        - label 100 GB Storage
        - label Priority Support
        - label Advanced Analytics
```

---

## Hierarchy Templates

### hierarchy-tree-tech-style-capsule-item — Org Chart
```infographic
infographic hierarchy-tree-tech-style-capsule-item
data
  title Organization Structure
  items
    - label CEO
      children
        - label CTO
          children
            - label Engineering
            - label DevOps
            - label QA
        - label CFO
          children
            - label Finance
            - label Accounting
        - label CMO
          children
            - label Marketing
            - label Sales
```

### hierarchy-structure — Generic Hierarchy
```infographic
infographic hierarchy-structure
data
  title Product Categories
  items
    - label Electronics
      children
        - label Computers
          children
            - label Laptops
            - label Desktops
        - label Mobile
          children
            - label Phones
            - label Tablets
    - label Software
      children
        - label Applications
        - label Services
```

---

## Chart Templates

### chart-pie-donut-plain-text — Donut Chart
```infographic
infographic chart-pie-donut-plain-text
data
  title Revenue by Region
  items
    - label North America
      value 42
    - label Europe
      value 28
    - label Asia Pacific
      value 18
    - label Other
      value 12
```

### chart-bar-plain-text — Bar Chart
```infographic
infographic chart-bar-plain-text
data
  title Top Products by Sales
  items
    - label Product A
      value 85
    - label Product B
      value 72
    - label Product C
      value 58
    - label Product D
      value 45
    - label Product E
      value 32
```

### chart-column-simple — Column Chart
```infographic
infographic chart-column-simple
data
  title Monthly Revenue
  items
    - label Jan
      value 120
    - label Feb
      value 150
    - label Mar
      value 180
    - label Apr
      value 165
    - label May
      value 200
```

### chart-wordcloud — Word Cloud
```infographic
infographic chart-wordcloud
data
  title Technology Trends
  items
    - label AI
      value 100
    - label Cloud
      value 85
    - label Blockchain
      value 60
    - label IoT
      value 55
    - label 5G
      value 50
    - label Quantum
      value 40
    - label AR/VR
      value 35
    - label Edge Computing
      value 30
```

---

## Quadrant Templates

### quadrant-quarter-simple-card — Priority Matrix
```infographic
infographic quadrant-quarter-simple-card
data
  title Priority Matrix
  items
    - label Do First
      desc Urgent & Important
      children
        - label Critical bugs
        - label Client deadlines
    - label Schedule
      desc Not Urgent & Important
      children
        - label Planning
        - label Training
    - label Delegate
      desc Urgent & Not Important
      children
        - label Meetings
        - label Some emails
    - label Eliminate
      desc Not Urgent & Not Important
      children
        - label Time wasters
        - label Busy work
```

---

## Relation Templates

### relation-circle-icon-badge — Central Concept
```infographic
infographic relation-circle-icon-badge
data
  title Digital Transformation
  items
    - label Cloud
      icon mdi/cloud
    - label Data
      icon mdi/database
    - label AI
      icon mdi/brain
    - label Security
      icon mdi/shield-lock
    - label Mobile
      icon mdi/cellphone
```

---

## With Theme Customization

### Dark Theme with Custom Palette
```infographic
infographic list-row-horizontal-icon-arrow
theme dark
  palette
    - #61DDAA
    - #F6BD16
    - #F08BB4
data
  title Process Steps
  items
    - label Start
      desc Begin here
      icon mdi/play
    - label Process
      desc Work in progress
      icon mdi/cog
    - label Complete
      desc Finish
      icon mdi/check
```

### Hand-drawn Style
```infographic
infographic sequence-snake-steps-simple
theme
  stylize rough
  base
    text
      font-family 851tegakizatsu
data
  title Creative Process
  items
    - label Ideate
      desc Brainstorm ideas
    - label Sketch
      desc Quick drawings
    - label Refine
      desc Polish concepts
    - label Deliver
      desc Final output
```
