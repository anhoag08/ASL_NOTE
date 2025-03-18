
> 1. Summary 
- The paper introduces the User Behavior Language (UBL), a specialized language designed to optimize user interface (UI) testing through easy-to-understand syntax and an automatic test case generation tool. 
- UBL not only simplifies the process of writing test scripts but also supports modeling complex workflows. 
- The effectiveness of the method is validated by comparing it with Katalon Studio through testing some functions of SauceDemo. 
  
2. Overall evaluation 
- Novelty and significance of the research 
	- The paper contributes to the field of UI testing, especially for those without a technical background. 
	- The development of a specialized language like UBL enhances the usability of UI testing, which is an important concern in software development. It focuses on addressing the challenges in creating UI test scripts, reducing the cost and time involved in the testing process. 
	- However, the authors should provide more arguments, analysis, and evaluation to clarify the applicability of UBL, especially highlighting cases where UBL cannot specify certain user actions. 
- Clarity and structure of the paper 
	- The structure of the paper is logical, from the introduction of the problem to the method, experimentation, evaluation, and discussion. 
	- The sections of the paper are clearly presented, with the main points outlined in a coherent manner. 
	- However, the experimentation and evaluation sections need to be supplemented with additional information to better explain the conclusions. 
	- Authors should consider adding a section related to tool support to be able to reproduce the experiment, increasing the clarity of the study. 
	  
3. Methodology 
- The research methodology is sound and well-founded. The authors employed a problem analysis method, proposed solutions, conducted experiments, and compared the performance of UBL and Katalon to evaluate the effectiveness of the UBL specification language. 
- The research methodology is built on a logical foundation, applying UBL to address the specific issue of UI test case creation. However, the study does not clearly define the scope of UBL's application for specific problem sets. Additionally, the supporting tools for creating UBL specifications and generating automated test cases are not described in detail. 
- Consequently, issues such as verifying the correctness (both syntax and semantics) of UBL specifications before using them as a basis for generating automated test cases remain unclear. 
  
4. Results and Analysis 
- The results are clearly presented, but the explanation needs to be more detailed, and additional practical test cases should be provided to increase the persuasiveness of the findings. 

5. Suggestions for improvement 
- Presentation layout and formatting 
	- The description of the paper's structure on page 2 lacks an introduction to Section 5 (Evaluation). 
	- Inconsistent terminology is used; for example, the action of filling a text box is described by two distinct terminologies "fill" (Table 1 and Figure 5), "input" (Fig. 4, 6, 7). 
- Content 
	- A high-level specification language often faces situations where users make incorrect command statements. 
	- The authors have not clarified whether the UBL tool supports automatic detection of syntax/semantic errors in specifications. If not, what measures are in place to ensure the correctness of specifications before using them as a basis for generating automatic test cases? 
	- Typical errors include: using incorrect user actions on HTML DOM objects (e.g., $<fill> <a radio button>$) or using incorrect relational operators (e.g., $<select>$ “Ha Noi” to province | $<select>$ “Hoan Kiem” to district, where both province and district are required parts of a valid address). - On page 4 (at the end of Section 2), the identification of the script set based on the Sequence of Actions (SoA) containing constraints is not well-defined. 
	- The authors need to clarify the selection of (n+1) test cases generated for a disjunction (|) of n-Commands. The metrics or coverage criteria for selecting these (n+1) test cases are unclear. 
	- In this situation, determining the number of test cases for each input must be linked to one or more constraints on its data domain. Where these constraints are determined by the element's data type and business rules on the element (if any). 
	- In this study, the authors compare UBL and Katalon in terms of performance and the speed of learning how to use the tool. Clearly, the scope of application and expressiveness of the language strongly influence the learning curve and performance of the tool, but the study does not clarify or compare the scope of application of UBL with Katalon. Katalon supports many user actions (e.g., drag and drop, scroll to elements, double click, right click, upload files, etc.) and system actions that UBL does not support. Therefore, the study needs to further address this issue.  
	- The study proposes a specification language, so the author needs to state formal definitions for the elements of the UBL metamodel (test scenario, SoA, Command, Constraint) instead of explaining through illustrative examples, which is difficult to follow and does not clarify the scope of the specifying domain of the domain-specific language. - According to the metamodel explanation in Section 2, a command consists of two parts $<action> <targeted element>$ , so the $<action>$ A | $<action>$ B declaration consists of two separate commands $<action>$ A and $<action>$B (included in two distinct SoA). So here it is clear that there exists a constraint relationship between the SoAs specified by the constraint “|”. There are cases where 3,4-fold relationship constraints between actions often occur on web UI but have not been mentioned. For example, a valid shipping address must include 3 administrative address levels and a detailed address instruction (street, hamlet, block). 
	- The metamodel should also clearly distinguish between user actions and verify actions as well as the possible relationships between them. 
	- In Table 2, Section 5 (Evaluation), the paper compares the performance and learning speed of UBL with Katalon. A question arises about the fairness of this comparison. This comparison does not take into account the time to create the UBL specification, but only considers the time to generate test cases from the UBL specification. 
	- It would be more objective to compare the total time (including the time to create the UBL specification and the time to generate test cases from the UBL specification) with the time to generate test cases in different ways using Katalon such as (1) recording & replaying and adjusting keyword sets to create a full test case set, (2) manually writing test cases, and (3) creating Gherkin specifications and automatically generating test cases from Gherkin specifications. 
	
6. Final recommendation Resubmit for review: The paper could be accepted if the authors make the necessary revisions based on the suggestions.