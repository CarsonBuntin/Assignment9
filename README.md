Tasks to answer in your own README.md that you submit on Canvas:

1. See logger.log, why is it different from the log to console?
    
    Answer: logger.log allows us to report and persist error messages while console log only prints text
    to the screen. logger.log also allows messages to later be retrieved.

2. Where does this line come from? FINER org.junit.jupiter.engine.execution.ConditionEvaluator logResult Evaluation of condition
    [org.junit.jupiter.engine.extension.DisabledCondition] resulted in: ConditionEvaluationResult [enabled = true, reason = '@Disabled is not present']
    
    Answer: FINER outputs a detailed tracing message and may include logging calls regarding method entering, exiting, 
    throwing exceptions.

3. What does Assertions.assertThrows do?
    
    Answer: The assertThrows method asserts that execution of the supplied executable would throw an exception of the 
    expectedType parameter and of any exception the expectedType parameter is a subtype of. If the exception is thrown the 
    test passes otherwise it fails.

4. See TimerException and there are 3 questions
    1.  What is serialVersionUID and why do we need it? (please read on Internet)
        
        Answer: serialVersionUID is used for serialization, it should be used in any class to check if a serialized class 
                matches the class definition you're trying to deserialize it into.
    
    2.  Why do we need to override constructors?
    
        Answer: The reason that the constructor is overwritten is that a timer exception could be thrown for multiple scenarios
        one being if none throwable event happens that is still an error you only need a message and not a throwable class.
        if the exception is in a catch block with a throwable message than the other constructor is needed. lastly
        there need to be a constructor with a null parameter, so it can be used as a throwable in a catch block.
    
    3.  Why we did not override other Exception methods?
            
        Answer: Because the class we were testing the timer class and did not want to tamper with any of the other exceptions. 
        we created the TimerException class in order to create catered exceptions for the timer class.
    
5. The Timer.java has a static block static {}, what does it do? (determine when called by debugger)
        
    Answer:  A static method can only access static members, can be called without an instance and are not associated 
    with an object.

6. What is README.md file format how is it related to bitbucket? (https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html)
   
    Answer: README.md file format is called Markdown Syntax and If your repository contains a README.md file at the root 
    level, Bitbucket displays its contents on the repository's Source page if the file has the .md extension.

7. Why is the test failing? what do we need to change in Timer? (fix that all tests pass and describe the issue)
    
    Answer: We needed to move the time now initialization out of the try block and into the finally block because once the
    TimerException is thrown it immediately jumps to the finally block causing the program to throw a null pointer due to the
    fact that timeNow was never initialized.

8. What is the actual issue here, what is the sequence of Exceptions and handlers (debug)
    
    Answer: The actual issue is that the TimerException is being overriten by th nullPointer exception
    causing the test to fail.

9. Make a printScreen of your eclipse JUnit5 plugin run (JUnit window at the bottom panel) 
    
    Answer: See screenshot turned into canvas.

10. Make a printScreen of your eclipse Maven test run, with console
11. What category of Exceptions is TimerException and what is NullPointerException
    
    Answer: NullPointerException is a RuntimeException and TimerException is just a standard Exception.

12. Push the updated/fixed source code to your own repository.