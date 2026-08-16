# Proteus Style Guide for C/C++

This document defines the naming, organization, and interoperability
conventions for C and C++ code in Proteus. The goal is consistency: anyone
reading Proteus code should be able to tell what a symbol is — enum, global,
macro, member — just by looking at it.

---

## Quick Reference

| Category                           | Convention         | Example                             |
|------------------------------------|--------------------|-------------------------------------|
| Enums                              | `k_` prefix        | `k_MaxPlayers`                      |
| Globals                            | `g_` prefix        | `g_Renderer`                        |
| Scoped statics                     | `s_` prefix        | `s_InstanceCount`                   |
| Functions (public)                 | PascalCase         | `UpdateTransform()`                 |
| Functions (private/protected)      | `__` + camelCase   | `__checkFilePermissionsPosixImpl()` |
| Variables (local/params/members)   | camelCase          | `deltaTime`                         |
| Private/protected member variables | `__` + camelCase   | `__cachedTransform`                 |
| Constants                          | camelCase, no prefix | `maxRetryCount`                   |
| Macros                             | UPPER_SNAKE_CASE   | `PROTEUS_ASSERT(x)`                 |
| Header guards                      | `#pragma once`     | —                                   |