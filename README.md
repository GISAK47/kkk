# kkk
openai.api_key = "Your API key here"
def say(text):
subprocess.call(["say", text])
def get_answer(prompt, temperature):
response = openai.Completion.create(
engine="text-davinci-003",
max_tokens= 1024,
prompt=prompt,
temperature=temperature
)
return response["choices"][0]["text"]
def main():
while True:
prompt1 = get_answer("Ask something from an another chatbot!", 0.7)
answer1 = get_answer(prompt1, 0.7)
print("Chatbot 1: " + answer1)
subprocess.call(["say", answer1])
prompt2 = get_answer(answer1, 0.9)
answer2 = get_answer(prompt2, 0.9)
print("Chatbot 2: " + answer2)
subprocess.call(["say", answer2])
if __name__ == "__main__":
main()
