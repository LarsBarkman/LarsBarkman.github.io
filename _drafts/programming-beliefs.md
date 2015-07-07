---
layout: post
title: My Beliefs about Systems Development and Architecture
---

<h1>My Beliefs about Systems Development and Architecture</h1>
<h2>Polyglot</h2>
<h2>Empathy</h2>
<h2>Curiosity</h2>
<h2>Creativity</h2>
<h2>Agile</h2>
<h2>Microservices</h2>
<h2>Distributed Systems</h2>
<h2>Event-driven Architecture</h2>
<h2>All Services Could be External</h2>
<ul>
  <li>All services should be built so that they could be externalized
<ul>
  <li>Documentation</li>
  <li>Security</li>
  <li>Scalability</li>
</ul>
</li>
</ul>
<h2>Platform team to support everybody else</h2>
<ul>
  <li>If you have a platform that everybody is developing on the platform team should be the most service oriented group in the whole company
<ul>
  <li>They have the teams as customers</li>
</ul>
</li>
</ul>
<h2>Coding Architects</h2>
Architects should be part of the development otherwise they will end up in a ivory tower
<h2>Light Weight Messaging</h2>
<ul>
  <li>Pub-Sub through a light weight messaging stack i.e. Apache kafka.</li>
  <li>ESB looks good on a architectural sketch but in reality it will end up like a spaghetti box on the inside</li>
</ul>
<h2>COTS</h2>
<ul>
  <li>COTS are great when the following attributes are met
<ul>
  <li>The system has "100%" of the functionality (don't extend only configure)</li>
  <li>The context is "systems of record" (don't innovate with COTS)</li>
  <li>The System don't cross context boundaries</li>
  <li>The system can be kept standard and process can be changed</li>
  <li>The system has the same API standard as the rest of the landscape</li>
  <li>The system should be able to be used without a UI only API</li>
  <li></li>
</ul>
</li>
</ul>
<h2>Cluster</h2>
Infrastructure separated from the platform so that infrastructure can be added to the platform without effecting the applications
<h2>The Landscape as Islands of Qualities</h2>
The platform should be islands of qualities that the containers can be deployed on
<h2>Micro-PaaS</h2>
PaaS as Container Host rather than building applications direct on PaaS
<h2>Infrastructure as Code</h2>
<h2>Conways Law</h2>
<h2>DevOps</h2>
<h2>Boyds Law</h2>
<h2>Continuous...</h2>
Continuous Delivery, Continuous Integration, Continuous Design
<h2>Autonomous End2End Teams</h2>
Teams building applications and deploying it to the platform
<h2>In House development/Insourcing</h2>