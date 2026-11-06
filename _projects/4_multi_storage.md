---
layout: page
title: Multi-Driver Storage Module
description: One upload interface for AWS S3, Azure Blob, Google Cloud Storage and local disk, so you can switch providers without touching business logic.
importance: 4
category: work
---

_Professional project at Riseup Labs._

A file upload module behind one shared interface, with drivers for:

- **AWS S3**
- **Azure Blob Storage**
- **Google Cloud Storage**
- **Local storage**

Switching storage providers is a configuration change. The business logic doesn't change.

This sat inside a backend I designed from scratch, which also included:

- A cache manager
- **JWT authentication** with refresh tokens
- A security layer with route guards, interceptors, CORS, rate limiting and request sanitisation

### Tech

`Node.js` · `Nest.js` · `AWS S3` · `Azure Blob` · `GCS` · `Redis` · `JWT`
