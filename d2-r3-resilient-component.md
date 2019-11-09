# Resilient Component Libraries in React

User interface design and development

How to build a ui
- get a statoc mockup from designer
- write html
- write css
- "Sprinkle" Javascript
- Hand off to backend bdeveloper
- replace html with php
- deploy

How to build a UI with React
- Get a staic mockup

dribble.com

HTML was developed for documents, not for applications

Component is a better way to render HTML

Component as a common languaget between developers, POs, designers and etc.

Design Tokens
===
Everything you use more than once in styles

Primitive components

Basic Primitives

CSS + React way = styled-system (styled-system.com)

import { color,margin, typography } from 'style-system'

const TextStyle = styled.p(
    { m: 12, color: "red" },
    color, margin, typography
)