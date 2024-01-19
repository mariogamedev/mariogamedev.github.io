---
title: "Gravitational Physics .NET App"
date: 2023-11-19T19:12:00-00:00
categories:
  - Code
tags:
  - C#
  - .NET
  - Physics
---

**C# Code Showcase: Physics Gravitational Field Effects Application**

Explore my showcase featuring C# code that demonstrates the gravitational field effects on other bodies. This application serves as a compelling use case for physics simulations, covering a range of scenarios. Immerse yourself in a display of good coding practices and thoughtful implementation, showcasing the versatility and efficiency of C# in a physics-oriented context.

Explore a brief code snippet that provides a glimpse into the solution's implementation:

```c#
﻿namespace GravitationalFieldEstimator
{
	public class Solver
	{
		private readonly float _gravitationalConstant;

		private IStatementParser _statementParser;
		private IGravitationalMovable _gravitationalMover;

		public Solver(IStatementParser statementParser, float gravitationalConstant)
		{
        _statementParser = statementParser;
        _gravitationalConstant = gravitationalConstant;
		}

		public void Initialize()
		{
        _statementParser.Parse();
        GravitationalField field = new GravitationalField(_gravitationalConstant);
        _gravitationalMover = new UniformGravitationalMover(field, _statementParser.Planet, _statementParser.Meteor);
    }

      public void Solve()
      {
          foreach (Vector2D timeEntry in _statementParser.TimeDistribution)
          {
              for (int i = 0; i < timeEntry.Y; i++)
              {
                  Vector2D estimatedPosition = _gravitationalMover.EstimatePosition(timeEntry.X);
                  Console.WriteLine($"{estimatedPosition.X:F2} {estimatedPosition.Y:F2}");
              }
          }
      }
	}
}
```

Check out the [Gravitational Field project][jekyll-gh] source code repo on Github.

[jekyll-gh]: https://github.com/mariogamedev/GravitationalFieldEstimator
