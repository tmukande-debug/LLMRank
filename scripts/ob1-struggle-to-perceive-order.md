## Observation 1. LLMs struggle to perceive order of user histories

LLMs can utilize historical behaviors for personalized ranking, but *struggle to perceive the order* of the given sequential interaction histories.

**LLMs can give personalized recommendations corresponding to prompts with historical behaviors.**

<div align="center"> 
<img src='../assets/2-a-user-his.png' width="30%">
<div>Figure 2 (a)</div>
</div>

- Ours

    ```bash
    cd llmrank/

    # ML-1M
    python evaluate.py -m Rank

    # Games
    python evaluate.py -m Rank -d Games
    ```

- No History

    ```bash
    cd llmrank/

    # ML-1M
    python evaluate.py -m NoHis

    # Games
    python evaluate.py -m NoHis -d Games
    ```

- Fake History

    ```bash
    cd llmrank/

    # ML-1M
    python evaluate.py -m FakeHis

    # Games
    python evaluate.py -m FakeHis -d Games
    ```

**LLMs struggle to perceive the order of the given historical user behaviors.**

<div align="center"> 
<img src='../assets/2-b-order.png' width="30%">
<div>Figure 2 (b)</div>
</div>

- Ours

    ```bash
    cd llmrank/

    # ML-1M
    python evaluate.py -m Rank

    # Games
    python evaluate.py -m Rank -d Games
    ```

- Ours (Random Order)

    ```bash
    cd llmrank/

    # ML-1M
    python evaluate.py -m RandOrder

    # Games
    python evaluate.py -m RandOrder -d Games
    ```

<div align="center"> 
<img src='../assets/2-c-his-len.png' width="30%">
<div>Figure 2 (c)</div>
</div>

- Ours

    ```bash
    cd llmrank/

    # ML-1M
    for length in 5 10 20 50
    do
        python evaluate.py -m Rank --max_his_len=${length}
    done
    ```
