<script setup>
import { ref, computed } from 'vue';

// Questions, Options, and Answers
const questions = ref([
  {
    question: 'Which is not a Javascript Data Type?',
    answer: 3,
    options: [
      'A Boolean',
      'Undefined',
      'String',
      'Double'
    ],
    selected: null
  },
  {
    question: 'What is THIS in Javascript?',
    answer: 0,
    options: [
      'the THIS keyword refers to an object',
      'the THIS keyword refers to a variable',
      'the THIS keyword refers to an array'
    ],
    selected: null
  },
  {
    question: 'What is a function in Javascript?',
    answer: 2,
    options: [
      'what happens when something is returned',
      'code that assigns a simple value to a variable',
      'a block of code designed to perform a particular task',
      'something the browser does, or something a user does'
    ],
    selected: null
  },
  {
    question: 'What is TypeScript?',
    answer: 2,
    options: [
      'A component based UI Approach.',
      'A Javascript Framework based on MVC Architecture',
      'A superset of JS created by Microsoft that allows for async, optional type, and classes.',
      'A group of objects'
    ],
    selected: null
  },
  {
    question: 'Collections in Javascript...',
    answer: '3',
    options: [
      'Used especially for the development of network-based applications',
      'Integration with other backend and frontend technologies',
      'adds interaction to otherwise static web pages and makes them react to users’ inputs.',
      'represent categories of data showcased through various data types.'
    ],
    selected: null
  },
  {
    question: 'What is an array?',
    answer: '0',
    options: [
      'An object enables storing a collection of multiple items under a single variable name,and has members for performing common array operations.',
      'An object that provide a mechanism for reading and writing raw binary data in memory buffers.',
      'It is used to assign a number to a variable',
      'A locally declared variable related to a function that stays in memory when it has returned'
    ],
    selected: null
  },
  {
    question: 'What is DOM?',
    answer: '0',
    options: [
      'The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page. ',
      'A piece of data stored on your computer to be accessed by your browser.',
      'none of the above'
    ],
    selected: null
  },
  {
    question: 'What is a serveless model?',
    answer: '1',
    options: [
      'a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.',
      'a cloud-native development model that allows developers to build and run applications without having to manage servers.',
      'adds interaction to otherwise static web pages and makes them react to users inputs.',
      'none of the above'
    ],
    selected: null
  },
  {
    question: 'What is the Git?',
    answer: '1',
    options: [
      'It is used for testing both synchronous and asynchronous JavaScript codes.',
      'A DevOps tool used for source code management. It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.',
      'having global scope are available everywhere in a JavaScript code',
      'none of the above'
    ],
    selected: null
  },
  {
    question: 'What is Pair Programming?',
    answer: '3',
    options: [
      'a cloud-native development model that allows developers to build and run applications without having to manage servers.',
      'adds interaction to otherwise static web pages and makes them react to users’ inputs.',
      'A DevOps tool used for source code management. It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.',
      'a software development technique in which two programmers work together at one workstation'
    ],
    selected: null
  },
  {
    question: 'What is CORS?',
    answer: '0',
    options: [
      'an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources.',
      'allows a site to prevent itself from loading (potentially malicious) content from unexpected sources',
      'none of the above'
    ],
    selected: null
  }, {
    question: 'What is GraphQL?',
    answer: '1',
    options: [
      'is a software architectural style that defines a set of constraints for creating Web services.',
      'is an application layer server-side technology that is used for executing queries with existing data',
      'none of the above'
    ],
    selected: null
  }, {
    question: 'What is RESTful API?',
    answer: '1',
    options: [
      'is an application layer server-side technology that is used for executing queries with existing data',
      'is a software architectural style that defines a set of constraints for creating Web services.',
      '',
      ''
    ],
    selected: null
  },
  {
    question: 'What is Observer Pattern?',
    answer: '3',
    options: [
      'when you repeatedly execute the same lines of code a specific number of times or as long as a specific condition is true',
      'is used for grouping the desired functions, variables, etc., under a unique name',
      'immutable data to tell the program exactly what to do',
      'A pattern that offers a subscription model in which objects subscribe to an event and get notified when the event occurs.'
    ],
    selected: null
  },
  {
    question: 'What is the difference between GET and POST?',
    answer: '1',
    options: [
      'POST is used to update an existing resource',
      'GET requests the data from a specified resource. POST submits the processed data to a specified resource.',
      'GET creates a new resource',
      'POST requests the data from a specified resource'
    ],
    selected: null
  },
  {
    question: 'What is OOP?',
    answer: '0',
    options: [
      'It is a computer programming model that organizes software design around data, or objects, rather than functions and logic.',
      'It is a computer programming model that uses immutable data to tell the program exactly what to do'
    ],
    selected: null
  },
  {
    question: 'What is the difference between PUT and POST?',
    answer: '0',
    options: [
      'PUT is used to update an existing resource, while the POST is used to create a new resource.',
      'POST is used to update an existing resource, while the PUT is used to create a new resource.',
      'none of the above'
    ],
    selected: null
  },
  {
    question: 'What is ReactJS?',
    answer: '3',
    options: [
      'responsible for managing all the packages and modules for Node.js',
      'a progressive JavaScript framework that is designed to be easy to use and scale. It is one of the newer frameworks on the scene, but it has already gained a lot of traction among developers. One of the reasons for its popularity is its flexibility; VueJS can be used for both small and large projects.',
      'an open-source JavaScript runtime environment that runs on multiple platforms and allows you to build scalable network applications quickly and easily.',
      'is an open-source JavaScript framework and library developed by Facebook. It is used for building interactive user interfaces and web applications quickly and efficiently with significantly less code than you would with vanilla JavaScript.'
    ],
    selected: null
  },
  {
    question: 'What is VueJS?',
    answer: '1',
    options: [
      'an open-source JavaScript runtime environment that runs on multiple platforms and allows you to build scalable network applications quickly and easily.',
      'a progressive JavaScript framework that is designed to be easy to use and scale. It is one of the newer frameworks on the scene, but it has already gained a lot of traction among developers. One of the reasons for its popularity is its flexibility; VueJS can be used for both small and large projects.',
      'responsible for managing all the packages and modules for Node.js',
      'an open-source, cross-platform JavaScript runtime environment and library to run web applications outside the clients browser. It is used to create server-side web applications.',
    ],
    selected: null
  },
  {
    question: 'What is NodeJS?',
    answer: '0',
    options: [
      'an open-source JavaScript runtime environment that runs on multiple platforms and allows you to build scalable network applications quickly and easily.',
      'a flexible and minimal Node.js web application framework that offers a comprehensive set of features for mobile and web applications.',
      'an open-source, cross-platform JavaScript runtime environment and library to run web applications outside the clients browser. It is used to create server-side web applications.',
      'responsible for managing all the packages and modules for Node.js'
    ],
    selected: null
  },
  {
    question: 'What is AngularJS?',
    answer: '2',
    options: [
      'a flexible and minimal web application framework that offers a comprehensive set of features for mobile and web applications.',
      'an open-source, cross-platform JavaScript runtime environment and library to run web applications outside the clients browser. It is used to create server-side web applications.',
      'a framework for creating dynamic web applications. It allows you to utilize HTML as the language of your templates and uses HTML syntax to express the components of your application clearly and succinctly'
    ],
    selected: null
  },
  {
    question: 'What is Express.js?',
    answer: '2',
    options: [
      'an open-source, cross-platform JavaScript runtime environment and library to run web applications outside the clients browser. It is used to create server-side web applications.',
      'responsible for managing all the packages and modules for Node.js',
      'a flexible and minimal web application framework that offers a comprehensive set of features for mobile and web applications.'
    ],
    selected: null
  },
  {
    question: 'What is MERN Stack?',
    answer: '0',
    options: [
      'Stacks prepared based on compatibility between different technologies. MERN stands for MongoDB, Express.Js, React.Js, Node.Js',
      'Stacks created whenever a variable that is defined outside the current scope is accessed within the current scope',
      'Stacks used when there is a need for a conditional declaration of a function',
    ],
    selected: null
  },
  {
    question: 'What ways can one create a new database in PostgreSQL?',
    answer: '2',
    options: [
      'Using pgAdmin | In this method, we use the GUI provided by pgAdmin to create the PostgreSQL database.',
      'Using SQL Shell | Here, in this method, we use the CLI provided by the SQL. Users have to write commands in the SQL shell for the creation of a new database.',
      'All of the above'
    ],
    selected: null
  },
  {
    question: 'What is PostgreSQL?',
    answer: '3',
    options: [
      'it is commonly used in constructors to assign values to object properties.',
      'a JavaScript function that is passed to another function as an argument or a parameter.',
      'a small data that is sent from a website and stored on the machine by a web browser that was used to access the website',
      'is an advanced version of SQL which provides support to different functions of SQL like foreign keys, subqueries, triggers, and different user-defined types and functions'
    ],
    selected: null
  },
  {
    question: 'What is a data structure?',
    answer: '0',
    options: [
      'a data structure is a format to organize, manage and store data in a way that allows efficient access and modification.',
      'a lightweight, interpreted programming language',
      'Used especially for the development of network-based applications',
      'none of the above'
    ],
    selected: null
  },
])

const quizCompleted = ref(false)
const currentQuestion = ref(0)

// Returns Score
const score = computed(() => {
  let value = 0
  questions.value.map(q => {
    if (q.selected == q.answer) {
      value++
    }
  })
  return value
})

// Returns Current Question
const getCurrentQuestion = computed(() => {
  let question = questions.value[currentQuestion.value]
  question.index = currentQuestion.value
  return question
})

// Sets Answer
const SetAnswer = evt => {
  questions.value[currentQuestion.value].selected = evt.target.value
  evt.target.value = null
}

// Moves to Next Question
const NextQuestion = () => {
  if (currentQuestion.value < questions.value.length - 1) {
    currentQuestion.value++
  } else {
    quizCompleted.value = true
  }
}

</script>

<template>
  <main class="app">
    <div class="icons">
      <img src="/vite.svg" height="70">
      <img src="/plus.svg" class="plus" height="15">
      <img src="/vue.svg" height="70">
    </div>
    <h1>Full Stack Quiz App</h1>
    <section class="quiz" v-if="!quizCompleted">
      <div class="quiz-info">
        <span class="question">{{ getCurrentQuestion.question }}</span>
        <span class="score">Score {{ score }}/{{ questions.length }}</span>
      </div>

      <div class="options">
        <label v-for="(option, index) in getCurrentQuestion.options" :key="index" :class="`option ${getCurrentQuestion.selected == index
          ? index == getCurrentQuestion.answer
            ? 'correct'
            : 'wrong'
          : ''
          } ${getCurrentQuestion.selected != null &&
            index != getCurrentQuestion.selected
            ? 'disabled'
            : ''
          }`">
          <input type="radio" :name="getCurrentQuestion.index" :value="index" v-model="getCurrentQuestion.selected"
            :disabled="getCurrentQuestion.selected" @change="SetAnswer">
          <span>{{ option }}</span>
        </label>
      </div>
      <button @click="NextQuestion" :disabled="!getCurrentQuestion.selected">
        {{
          getCurrentQuestion.index == questions.length - 1
          ? 'Finish'
          : getCurrentQuestion.selected == null
            ? 'Select an Option'
            : 'Next Question'
        }}
      </button>
    </section>
    <section v-else>
      <h2>You have finished the Quiz!</h2>
      <p>Your score is {{ score }} / {{ questions.length }}</p>
    </section>
  </main>
</template>

<style>
:root {
  --font-color: #424242;
  --bg-color: #fff;
  --quiz-color: #e0e0e0;
  --selection-color: #efefef;
  --heading-color: #292922;
}

.dark-theme {
  --font-color: #f1f1f1;
  --bg-color: #232327;
  --quiz-color: #2f2f35;
  --selection-color: #3b3b42;
  --heading-color: #f5f5f5;
}

* {
  margin: 0;
  padding: 0;
  font-family: 'Merriweather', sans-serif;
}

body {
  background-color: var(--bg-color);
  color: var(--font-color);
}

.app {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
  min-height: 100vh;
}

h1 {
  font-size: 2rem;
  margin-bottom: 2rem;
}

.quiz {
  background-color: var(--bg-color);
  padding: 1rem;
  width: 100%;
  max-width: 640px;
  border-radius: 0.5rem;
}

.quiz-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
}

.quiz-info .question {
  color: var(--heading-color);
  font-size: 1.25rem;
}

.quiz-info .score {
  color: var(--font-color);
  font-size: 1.25rem;
}

.options {
  margin-bottom: 1rem;
}

.option {
  display: block;
  padding: 1rem;
  background-color: var(--quiz-color);
  margin-bottom: 0.5rem;
  border-radius: 0.5rem;
  cursor: pointer;
}

.option:hover {
  background-color: var(--selection-color);
}

.option.correct {
  background-color: #37fc99;
}

.option.wrong {
  background-color: #ff545a;
}

.option:last-of-type {
  margin-bottom: 0;
}

.option.disabled {
  opacity: 0.5;
}

.option input {
  display: none;
}

button {
  appearance: none;
  outline: none;
  border: none;
  cursor: pointer;
  padding: .5rem 1rem;
  background-color: #37fc99;
  color: #2d213f;
  font-weight: 700;
  text-transform: uppercase;
  font-size: 1.25rem;
  border-radius: 0.5rem;
}

button:disabled {
  opacity: 0.5;
}

h2 {
  font-size: 2rem;
  margin-bottom: 2rem;
  text-align: center;
}

p {
  color: var(--font-color);
  font-size: 1.25rem;
  text-align: center;
}
</style>