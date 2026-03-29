# Reflection (Yarden Sasson)

## Learning

Working on this project made me learn that there is more than one way to perform a single task. When we learned how to do LDA in class, it was taught to us by only using the Bag of Words method. During this assignment, I was told to perform LDA using the CountVectorizer method. Although it was challenging, there are different ways to perform each analysis and each one of them have their own tradeoffs. Topic modeling is also very different from everything else that we have done in class so far because of the fact that it only requires the major words that were given by the person in the review. This means that it is easy to eliminate words that add emotion, emphasis, etc. when looking at the model initially. This could be more important when coming up with the topics later on, but it is important to separate in when determining the number of topics. 

Another thing that was important that I learned was the importance of pre-processing the text when it comes to topic modeling. This time we took the pre-processing to a different level by adding lemmatization to the pipeline. This step is very important in the topic modeling process because this process refers to the number of times a word is mentioned. When counting the number of times a word is mentioned, active versions of the word or past tense even can create noise within the model. This is why text cleaning is absolutely crucial and the choice of custom stopwords are important to the success of topic modeling. 

## Challenges

The main challenge that I faced specifically was taking the LDA example that was provided to us in class (using the Bag of Words method) and converting it to work with the CountVectorizer method. This was particularly difficult because Bag of Words works particularly well with the Genism library while the CountVectorizer method works with sklearn. With these conflicting libraries, it was very difficult for me to learn the respective functions from the sklearn library that specifically relate to this process. 

The second main issue that we had is working with the time. Running these simulations are particularly difficult because they take so much time, which made it difficult to make any immediate and necessary adjustments. This also made it hard to work collaboratively on GitHub with my partner. Without immediate access to the model, it would take hours to run the model and show the overall results. This delayed out ability to push new code files and can change the overall way my partner and I work together.

I that using AI really helped with debugging and working to fit the model to a new method.

Another challenge is that there are many topics that are optimal for each model we ran. 15 topics for 6 models means that we are coming up with over 90 topics which makes it more difficult to complete the full process between 2 people. 

The last main challenge that affected my ability was being very busy at work. A project at work really took over my life and prevented me from starting this event earlier. The weekend to the Wednesday of the week this assignment was due, I was in San Francisco planning an executing an event with over 45 Israeli Cybersecurity companies during one of the largest cybersecurity conferences in the world (RSA). The event I helped plan and execute generated over 800+ business meetings and took away my focus from school and other projects I had to work on. Being that my partner and I both work full time jobs, it was hard for us to complete this project in a timely manner. 


## Peer Evaluation 
I have worked with Brandon on other projects since we both started in the program. I think that this has been one of the hardest projects because we both have had busy schedules due to our jobs. Regardless of this, Brandon continues to be a great person to work with because no matter how much we have going on outside he will always pick up the phone and be a great sounding board and support to the project. Brandon's prior experience in topic modeling from his research at LMU continues to be beneficial and generates new insights that I never would have had. I am happy to work with Brandon because I can always count on him to help whenever it is necessary. Brandon also understands my work situation and contributes whenever he can.  
