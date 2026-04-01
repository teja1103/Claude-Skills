# AI Writing Patterns: Detailed Before/After Examples

Reference file for the humanizer skill. Each of the 30 patterns includes the problem description, words to watch, and concrete before/after examples.

---

## Content Patterns

### 1. Significance inflation

**Problem:** LLMs puff up importance by adding statements about how arbitrary aspects represent or contribute to broader topics.

**Before:**
> The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. This initiative was part of a broader movement across Spain to decentralize administrative functions and enhance regional governance.

**After:**
> The Statistical Institute of Catalonia was established in 1989 to collect and publish regional statistics independently from Spain's national statistics office.

---

### 2. Notability name-dropping

**Problem:** LLMs list media sources without context to assert importance.

**Before:**
> Her views have been cited in The New York Times, BBC, Financial Times, and The Hindu. She maintains an active social media presence with over 500,000 followers.

**After:**
> In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods.

---

### 3. Superficial -ing phrases

**Problem:** AI tacks present participle phrases onto sentences to add fake analytical depth.

**Before:**
> The temple's color palette of blue, green, and gold resonates with the region's natural beauty, symbolizing Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes, reflecting the community's deep connection to the land.

**After:**
> The temple uses blue, green, and gold colors. The architect said these were chosen to reference local bluebonnets and the Gulf coast.

---

### 4. Promotional language

**Problem:** LLMs can't keep a neutral tone, especially for cultural and travel topics.

**Before:**
> Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and stunning natural beauty.

**After:**
> Alamata Raya Kobo is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.

---

### 5. Vague attributions

**Problem:** AI attributes opinions to vague unnamed authorities.

**Before:**
> Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.

**After:**
> The Haolai River supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.

---

### 6. Formulaic challenges sections

**Problem:** AI includes formulaic "Despite challenges...continues to thrive" constructions.

**Before:**
> Despite its industrial prosperity, Korattur faces challenges typical of urban areas, including traffic congestion and water scarcity. Despite these challenges, with its strategic location and ongoing initiatives, Korattur continues to thrive as an integral part of Chennai's growth.

**After:**
> Traffic congestion increased after 2015 when three new IT parks opened. The municipal corporation began a stormwater drainage project in 2022 to address recurring floods.

---

## Language Patterns

### 7. AI vocabulary words

**Problem:** Certain words appear at far higher frequency in post-2023 AI-generated text. They often cluster together.

**Before:**
> Additionally, a distinctive feature of Somali cuisine is the incorporation of camel meat. An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**After:**
> Somali cuisine also includes camel meat, which is considered a delicacy. Pasta dishes, introduced during Italian colonization, remain common, especially in the south.

---

### 8. Copula avoidance

**Problem:** LLMs substitute elaborate verb constructions for simple "is"/"are"/"has".

**Before:**
> Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces and boasts over 3,000 square feet.

**After:**
> Gallery 825 is LAAA's exhibition space for contemporary art. The gallery has four rooms totaling 3,000 square feet.

---

### 9. Negative parallelisms

**Problem:** "Not only...but..." or "It's not just X, it's Y" constructions are overused.

**Before:**
> It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.

**After:**
> The heavy beat adds to the aggressive tone.

---

### 10. Rule of three

**Problem:** LLMs force ideas into groups of three to appear comprehensive.

**Before:**
> The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.

**After:**
> The event includes talks and panels. There's also time for informal networking between sessions.

---

### 11. Synonym cycling (elegant variation)

**Problem:** AI's repetition-penalty causes excessive synonym rotation for the same referent.

**Before:**
> The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.

**After:**
> The protagonist faces many challenges but eventually triumphs and returns home.

---

### 12. False ranges

**Problem:** LLMs use "from X to Y" where X and Y aren't on a meaningful scale.

**Before:**
> Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**After:**
> The book covers the Big Bang, star formation, and current theories about dark matter.

---

## Style Patterns

### 13. Em dash overuse

**Problem:** LLMs use em dashes far more than humans, mimicking punchy sales writing.

**Before:**
> The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues—even in official documents.

**After:**
> The term is primarily promoted by Dutch institutions, not by the people themselves. You don't say "Netherlands, Europe" as an address, yet this mislabeling continues in official documents.

---

### 14. Boldface overuse

**Problem:** AI mechanically emphasizes phrases in bold.

**Before:**
> It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)** and **Balanced Scorecard (BSC)**.

**After:**
> It blends OKRs, KPIs, and visual strategy tools like the Business Model Canvas and Balanced Scorecard.

---

### 15. Inline-header lists

**Problem:** AI outputs lists where every item starts with a bolded header + colon.

**Before:**
> - **User Experience:** The user experience has been significantly improved with a new interface.
> - **Performance:** Performance has been enhanced through optimized algorithms.
> - **Security:** Security has been strengthened with end-to-end encryption.

**After:**
> The update improves the interface, speeds up load times through optimized algorithms, and adds end-to-end encryption.

---

### 16. Title Case in headings

**Problem:** AI capitalizes all main words in headings.

**Before:**
> ## Strategic Negotiations And Global Partnerships

**After:**
> ## Strategic negotiations and global partnerships

---

### 17. Emojis in structure

**Problem:** AI decorates headings or bullet points with emojis.

**Before:**
> 🚀 **Launch Phase:** The product launches in Q3
> 💡 **Key Insight:** Users prefer simplicity
> ✅ **Next Steps:** Schedule follow-up meeting

**After:**
> The product launches in Q3. User research showed a preference for simplicity. Next step: schedule a follow-up meeting.

---

### 18. Curly quotation marks

**Problem:** ChatGPT uses curly quotes (\u201c...\u201d) instead of straight quotes ("...").

**Before:**
> He said \u201cthe project is on track\u201d but others disagreed.

**After:**
> He said "the project is on track" but others disagreed.

---

## Communication Patterns

### 19. Chatbot artifacts

**Problem:** Conversational filler from the chatbot interface gets left in the text.

**Before:**
> Here is an overview of the French Revolution. I hope this helps! Let me know if you'd like me to expand on any section.

**After:**
> The French Revolution began in 1789 when financial crisis and food shortages led to widespread unrest.

---

### 20. Knowledge-cutoff disclaimers

**Problem:** AI disclaimers about incomplete training data get left in text.

**Before:**
> While specific details about the company's founding are not extensively documented in readily available sources, it appears to have been established sometime in the 1990s.

**After:**
> The company was founded in 1994, according to its registration documents.

---

### 21. Sycophantic tone

**Problem:** Overly positive, people-pleasing language.

**Before:**
> Great question! You're absolutely right that this is a complex topic. That's an excellent point about the economic factors.

**After:**
> The economic factors you mentioned are relevant here.

---

## Filler and Hedging

### 22. Filler phrases

| Before | After |
|--------|-------|
| In order to achieve this goal | To achieve this |
| Due to the fact that it was raining | Because it was raining |
| At this point in time | Now |
| In the event that you need help | If you need help |
| The system has the ability to process | The system can process |
| It is important to note that the data shows | The data shows |

---

### 23. Excessive hedging

**Problem:** Over-qualifying every statement.

**Before:**
> It could potentially possibly be argued that the policy might have some effect on outcomes.

**After:**
> The policy may affect outcomes.

---

### 24. Generic positive conclusions

**Problem:** Vague upbeat endings that commit to nothing.

**Before:**
> The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence. This represents a major step in the right direction.

**After:**
> The company plans to open two more locations next year.

---

## Reasoning and Structure Patterns

### 25. Numbered-step reasoning where prose would be natural

**Problem:** AI defaults to numbered lists or "First...Second...Third..." for arguments and explanations that aren't actually sequential.

**Before:**
> There are several reasons why remote work has increased. First, the COVID-19 pandemic forced companies to adopt remote policies. Second, employees reported higher satisfaction with flexible schedules. Third, companies realized they could reduce office costs. Finally, advances in collaboration tools made remote work more practical.

**After:**
> Remote work took off because of COVID — that's the obvious part. But it stuck around because it turned out most people preferred it and companies liked cutting their lease costs. The tools caught up too, though honestly Zoom fatigue is its own problem.

---

### 26. Exhaustive balanced coverage

**Problem:** AI gives every subtopic equal weight, producing encyclopedia-style prose where every "aspect" gets its paragraph regardless of importance or interest.

**Before:**
> Tokyo is known for its history, culture, cuisine, technology, and natural beauty. The city's history dates back to the 15th century when it was known as Edo. Its culture blends traditional and modern elements. The cuisine ranges from street food to Michelin-starred restaurants. Technology innovation drives much of the economy. Natural attractions include parks and nearby Mount Fuji.

**After:**
> If you go to Tokyo, you eat. That's the point. The convenience stores alone are better than most restaurants I've been to in other cities. I had an egg sandwich from 7-Eleven at 2 AM that I still think about. The shrines and the Shibuya crossing and all that are worth seeing, sure, but the food is why you'd go back.

---

### 27. Connector addiction

**Problem:** Every sentence or paragraph opens with a transition word, creating a cadence that's immediately recognizable as AI-generated.

**Before:**
> The team decided to switch to TypeScript. Moreover, they adopted a stricter linting configuration. Furthermore, code reviews became mandatory for all pull requests. Additionally, they implemented automated testing. Consequently, bug rates dropped by 30%.

**After:**
> The team switched to TypeScript and got strict about linting and code reviews. Bug rates dropped 30%. Whether that's the TypeScript or the reviews is anybody's guess — they changed everything at once.

---

### 28. Abstraction over specifics

**Problem:** AI summarizes at a high level instead of showing concrete details. It gestures at specifics without providing them.

**Before:**
> The restaurant offers a variety of dishes that cater to different dietary preferences. Various factors contribute to its popularity, including the quality of ingredients and the creativity of the menu. Several reviews have highlighted the dining experience as exceptional.

**After:**
> They do a miso-glazed black cod that's genuinely excellent — the kind of dish where you scrape the plate. Portions are small for the price (the cod is $38), and the wait on weekends is easily an hour without a reservation.

---

### 29. Recursive summarization

**Problem:** AI restates what it just said at the end of paragraphs and sections. Conclusions echo introductions.

**Before:**
> Agile methodology emphasizes iterative development and frequent feedback. Teams work in short sprints to deliver incremental value. Stakeholders review progress regularly to ensure alignment. In summary, agile methodology focuses on iterative development, frequent feedback, and regular stakeholder reviews to deliver value incrementally.

**After:**
> Agile boils down to short sprints and frequent check-ins. Whether your team actually benefits from that depends a lot on whether your stakeholders show up to the reviews. In my experience, about half the time they don't, and then you're just doing waterfall with extra meetings.

---

### 30. Uniform confidence tone

**Problem:** Every sentence carries the same mid-level certainty. AI doesn't distinguish between things it's sure about, things it's guessing about, and things nobody knows.

**Before:**
> Exercise improves cardiovascular health. It also enhances mental well-being. Regular physical activity can reduce the risk of chronic diseases. Additionally, exercise has been shown to improve sleep quality and cognitive function.

**After:**
> Exercise is good for your heart — that's about as settled as anything in medicine. The mental health benefits are real too, though the mechanism is less clear. Sleep improvement? Probably, based on what I've read, but I've also had plenty of nights where a hard workout left me wired at midnight. Your mileage will vary.
