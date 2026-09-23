---
layout: page
title: Portfolio Analysis Engine
description: Live CAPM skill-vs-luck attribution on a real brokerage account · Python · NumPy/SciPy · pandas · Alpaca API
img: assets/img/portfolio-analysis-engine.png
importance: 1
category: work
redirect: https://grady-portfolio-dashboard.up.railway.app/
---

A locally-run (and cloud-deployable) web app that pulls a live Alpaca account and
produces an on-demand performance breakdown, including a **CAPM skill-vs-luck
attribution** that separates market/sector exposure (β) from benchmark-independent
return (α, with a two-sided t-test p-value).

Built with Python — NumPy/SciPy for the regression, pandas for the data plumbing —
and a standard-library-only web layer (no Flask/FastAPI). Credentials never leave
the process.

[Open the live dashboard →](https://grady-portfolio-dashboard.up.railway.app/)
