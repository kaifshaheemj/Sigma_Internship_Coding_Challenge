# Sigma_Internship_Coding_Challenge

# Sigma Internship Coding Challenge

## Goal

This exercise aims to familiarize participants with the Quantrocket platform, testing coding and algorithm skills, and setting up a minimalist trading workflow.

## Getting Started

1. *Install Quantrocket:* Either locally or on your preferred cloud platform. Begin with a few quick tutorials to grasp the basic capabilities of the platform.

2. *Data Acquisition:* Ensure you can pull daily close price data for Apple Inc. (AAPL) for the year 2023 (from 01-01-2023 to 12-31-2023). This data is part of the freely available US stock price data on Quantrocket.

## Daily Stock Trading Prompt

### Objective

Build a simple model to decide whether to place a buy order on day d+1 to maximize portfolio value, using pre-specified logic. Publish both the output and your code.

### Logic Details

- Let p(d) denote the close price on day d.
- Define returns r(d) as r(d) = (p(d) - p(d-1)) / p(d-1).
- Classify each day's state based on r(d) as follows:
  - if r(d) >= 0.1 then s(d) = +1 (Bull)
  - else if r(d) > -0.1 then s(d) = 0 (Flat)
  - else s(d) = -1 (Bear)

### Value Function

- Assuming a buy order on day d+1:
  - If s(d+1) = 1 & s(d) = 0, then V(d+1) = V(d) + 1
  - If s(d+1) = -1 & s(d) = 0, then V(d+1) = V(d) - 1
  - Otherwise, V(d+1) = V(d)

Your goal is to calculate the transition distribution in a streaming manner, deciding on optimal points for buy orders to maximize V(N).

### Submission Requirements

Submit the following in your GitHub repository:
- The final value V(N)
- The optimal buy indices
- Your source code

### Additional Information

Feel free to join the Sigma Slack group for any questions, or contact @Arpit Goel directly during the challenge.
