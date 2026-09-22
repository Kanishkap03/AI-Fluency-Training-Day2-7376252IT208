Day 2 Analysis

Topic

Comparison of different LLM reasoning approaches and agent-based problem solving.

1. ReAct Agent

The react_trace.py program uses the ReAct approach, where the system combines reasoning with actions and observations.

Process

The agent:

Gets the fees for CS101, AI202, and DS303 using the course-fee tool.

Calculates the cost of CS101 + AI202 after a 10% scholarship.

Calculates the cost of all three courses after a 25% scholarship.

Calculates the difference between the two options.

Result

CS101 + AI202 with 10% scholarship = Rs. 27,000

CS101 + AI202 + DS303 with 25% scholarship = Rs. 33,750

Difference = Rs. 6,750

Therefore, for this question, the two-course option costs Rs. 6,750 less.

Observation

The ReAct approach is useful when a problem requires external tools or multiple actions. The trace makes the sequence of tool calls and their results visible.

2. Chain-of-Thought Comparison

The cot_compare.py program compares the same questions using two prompting approaches:

Without CoT: the model is asked to provide only the final answer.

With CoT: the model is asked to solve the problem step by step and provide a final answer.

Question 1

Three courses cost Rs. 12,000, Rs. 18,000, and Rs. 15,000.

Total = Rs. 45,000

15% scholarship = Rs. 6,750

Amount after scholarship = Rs. 38,250

Each of 4 instalments = Rs. 9,562.50

Both approaches produced the same final answer.

Question 2

There are 18 computers.

Morning: 18 × 2 = 36 sittings

Afternoon: 18 × 3 = 54 sittings

Total = 36 + 54 = 90 sittings

Both approaches produced the same final answer.

Question 3

The height relationships are:

Ravi > Kumar > Arun > Priya

Therefore:

Tallest = Ravi

Shortest = Priya

Both approaches produced the same final answer.

Observation

For these three questions, the direct approach and the step-by-step approach produced matching final answers. The step-by-step approach provides more visible reasoning, while the direct approach is shorter.

3. Self-Consistency

The self_consistency.py program runs the same Chain-of-Thought prompt five times with a non-zero temperature so that the responses can vary.

Results

Run

Answer

1

Rs. 9,562.50 per instalment

2

Rs. 9,562.50 per instalment

3

Rs. 9,562.50

4

Rs. 9,562.50 per instalment

5

Rs. 9,562.50 per instalment

The same answer was obtained in all 5 runs. The program reported the majority answer as:

Rs. 9,562.50 per instalment

Observation

Self-consistency checks whether repeated model runs converge on the same answer. In this experiment, all five runs agreed, indicating consistent output for the given arithmetic problem.

4. Overall Comparison

Approach

Main idea

Result in this experiment

ReAct Agent

Uses tools through a sequence of actions and observations

Correctly calculated the course-cost comparison

Direct Prompt

Requests only the final answer

Correct answers for all three questions

Chain-of-Thought Prompt

Requests a step-by-step solution

Correct answers for all three questions

Self-Consistency

Runs the reasoning multiple times and selects the majority answer

All 5 runs produced the same answer

5. Key Learning

This experiment demonstrates that different LLM techniques serve different purposes:

ReAct is useful when the model needs to interact with tools or external functions.

Direct prompting is concise and suitable when only the final answer is needed.

Step-by-step prompting exposes intermediate calculations and can make the solution easier to inspect.

Self-consistency uses multiple model runs to check whether answers are stable across runs.

For the questions tested here, the approaches produced consistent correct answers. However, these results are specific to the tested questions and do not by themselves establish that one approach is universally more accurate than another.