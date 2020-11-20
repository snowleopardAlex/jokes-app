<!--
Create an app that render 5 <Question /> components. Each component should 
recieve a question prop and answer prop and render those however you like.
Some questions have no answers. If you don't pass in a answer prop, how might you make it only show the question instead?

const questionData = [
   {
        id: 1,
        question: "What is the capital of Poland?",
    },
    {
        id: 1,
        question: "What is the capital of Italy?",
        answer: "Rome"
    },
    {
        id: 1,
        question: "What is the capital of Argentina?",
        answer: "Buenos Aires",
    },
    {
        id: 1,
        question: "What is the capital of Russia?",
        answer: "Moscow"
    },

]

export default questionData;


import React from "react";
import Question from "./Question";
import questionData from "./questionData";

function App() {

  // higher order methods, map()
  const questionsComponent = questionData.map(question => 
    <Question key={question.id} question={question.question} answer={question.answer} />)

    return(
      <div className="exam" style={{textAlign: "center"}}>
        <h2>Exam</h2>
        {questionsComponent}
      </div>
    );
}

export default App;


import React from "react";

function Question(props) {
    return(
      <div className="exam-questions">
         <p style={{ color: !props.question && "#888888"}}>Question: {props.question}</p>
         <p style={{display: !props.question && "none"}}>Answer: {props.answer}</p>
      </div>
    );
}

export default Question;