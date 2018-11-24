# ECMAScript proposal: Stardatize deprecatation proccess/timelines and how to do it

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Многие годы JS развивается, добавляется новый функционал, но старые подходы не удаляются из языка. 
Согласовать процесс устаревшего отказа в языке программирования JS.

По аналогии с `"use strict";`:

Можно делать `"use es2018";` и отключать возможности которые в будущем пометять как deprecated.
Просто если не иметь этого процесса вовсем то будет больно в будущем.
