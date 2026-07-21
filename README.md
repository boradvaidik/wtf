# wtf
wtf
!pip install groq






SAMPLE_TICKET = ("Hi, I can't log into the VPN, it says my password expired "
                  "but the reset link isn't working. This is urgent, I have "
                  "a client call in 20 mins.")




# =====================================================================
# SECTION 7 — GenAI-Based AI (generation only)
# =====================================================================
from google.colab import userdata
import os
os.environ["GROQ_API_KEY"] = userdata.get("GROQ_API_KEY")


def draft_response_genai(ticket_text: str) -> str:
    from groq import Groq
    client = Groq()  # reads GROQ_API_KEY from env
    prompt = f"""You are an IT helpdesk assistant. A ticket came in:


"{ticket_text}"


Draft a short, empathetic resolution reply. If the ticket sounds urgent,
offer an immediate temporary workaround before the full fix. End with
one line: ESCALATE: yes/no.
"""
    response = client.chat.completions.create(
        # Groq retired llama-3.3-70b-versatile / llama-3.1-8b-instant in
        # 2026 -- check console.groq.com/docs/models for the current list.
        model="openai/gpt-oss-20b",
        max_tokens=500,
        messages=[{"role": "user", "content": prompt}],
    )
    return response.choices[0].message.content





<html>
<head>
<tittle>kush</title>
<body style="background-color:powerblue;"></head>
<h1><b>kush</b></h1>
<button>click me</button>
<a href="dfault.asp">
<img src="smiley.gif" alt="HTML tutorial"style=="width:42px;height:42px;">
</a>
<img src= patel.png></img>
</body>
</html>




print("\n" + "=" * 70)
    print("SECTION 7 — GenAI-Based AI (requires GROQ_API_KEY)")
    print(draft_response_genai(SAMPLE_TICKET))  # run this live with your key set"

