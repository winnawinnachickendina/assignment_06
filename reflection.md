# Reflection

## Instructions

Reflections are a metcognitive activity where you are encouraged to think about your own thinking. It helps you build a strong understanding of your own learning. A good learner not only "knows what they know", but they "know what they don't know", too. Learning to reflect takes practice, but if your goal is to become a self-directed learner where you can teach yourself things, reflection is imperative.

- Now that you've completed the assignment, think about what you did and share your thoughts. What did you learn? What confuses you? Where did you struggle? Where might you need more practice?
- A good reflection is: **specific as possible**,  **uses the terminology of the problem domain** (what was learned in class / through readings), and **is actionable** (you can pursue next steps, or be aided in the pursuit). That last part is what will make you a self-directed learner.
- Flex your recall muscles. You might have to review class notes / assigned readings to write your reflection and get the terminology correct.
- Your reflection is for **you**. Yes I make you write them and I read them, but you are merely practicing to become a better self-directed learner. If you read your reflection 1 week later, does what you wrote advance your learning?

Examples:

- **Poor Reflection:**  "I don't understand loops."   
**Better Reflection:** "I don't undersand how the while loop exits."   
**Best Reflection:** "I struggle writing the proper exit conditions on a while loop." It's actionable: You can practice this, google it, ask Chat GPT to explain it, etc. 
-  **Poor Reflection** "I learned loops."   
**Better Reflection** "I learned how to write while loops and their difference from for loops."   
**Best Reflection** "I learned when to use while vs for loops. While loops are for sentiel-controlled values (waiting for a condition to occur), vs for loops are for iterating over collections of fixed values."

`--- Write your reflection in the file code/reflection.txt ---`
In this assignment I learned how to call a REST API from Python using requests. The Azure endpoints want form data (data=), the AI endpoints want a JSON body (json=), and settings like the model name go in the query string (params=). I also learned that raise_for_status() stops the code right where an HTTP error happens, like a 401 for a bad API key, instead of letting it turn into a confusing KeyError later. I keep my key in a .env file so it never gets pushed to GitHub. Caching was a big idea for me: I check if the cache file exists, and if not I call the API once and save the answer with json.dump. That avoids the 150-request limit and makes debugging fast, because the transform steps just read the saved JSON. I also learned to separate extract (steps that call the network) from transform (steps that only reshape data). Using both opinion mining and entity recognition made sense to me because opinion mining catches things like “seating” and “music” in the same sentence with opposite feelings, but misses names like Pete and Otto, which entity recognition finds. The part I struggled with most was opinions_table. json_normalize couldn’t handle it because each target points to its assessments by reference, so I had to use nested loops and int(ref.split("/")[-1]) to find the right one. I also still get mixed up with record_path, meta and record_prefix. Finally, I learned the idea behind retrieval-augmented generation: pandas does the counting (the net column), and the language model only writes from the facts I give it. Next, I want to redo the json_normalize step from scratch without looking at my notes, and practice reading JSON that has nested lists.