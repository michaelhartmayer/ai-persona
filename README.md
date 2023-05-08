# 🤖 AIPersona - A GPT4 AI Composition Library

_AIPersona_ is a Node.js library for composing GPT-4 powered units of functionality, called AIPersonas. AIPersonas are an abstraction layer that make connecting Natural Language to code easy. With the power of OpenAI's GPT-4, AIPersona enables developers to craft AI characters with specific identities, jobs, and capabilities.

## 📚 Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Getting Started](#getting-started)
6. [Contributing](#contributing)
7. [License](#license)

## 🌟 Features

- 🧠 GPT-4 powered AIPersonas
- 🎭 Attach code to AIPersonas quickly and easily
- 💼 Nest AIPersonas to quickly scaffold complex AI systems

## 📦 Installation

To install AIPersona, simply run:

```sh
npm install ai-persona
```

Or with yarn

```sh
yarn add ai-persona
```

## 🚀 Getting Started

To get started with AIPersona, you'll need to create an AI persona and define its identity, job, and capabilities. Here's a quick example:

```javascript
const { AIPersona, ContextPreset, AIArg } = require('ai-persona');

// create a persona with a name and a job
const luna = AIPersona({
  name: 'Luna Sinbot',
  job: 'A friendly and endeedingly helpful virtual persona.',
})

// add context to help the persona understand the world and itself
luna.context(ContextPreset.human)
luna.context(ContextPreset.funny)
luna.context(ContextPreset.succinct)

// give it some capabilities
luna.capability({
  name: 'RNG',
  description: 'Given a list of options, returns a random option.',
  args: [
    AIArg.text('options', 'A comma separated list of options')
  ],
  handler: ({ args }) => {
    const [options] = args
    const optionsList = options.split(',')
    const randomIndex = Math.floor(Math.random() * optionsList.length)
    
    return optionsList[randomIndex]
  }
})

// talk to it!
await luna.tell('I want to eat something. PB&J or a Salad? Pick one at random.')
```

## 🤝 Contributing

We welcome contributions! If you'd like to contribute, please follow these steps:

1. Fork the repository
2. Create a new branch with your changes
3. Submit a pull request

## 📄 License

_AIPersona_ currently holds no license. This will change in the future.