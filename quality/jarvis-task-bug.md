# A reply without a saved task

[Polski](jarvis-task-bug.pl.md) · [Jarvis](../projects/jarvis/README.md)

**Project:** Jarvis · **Date:** November 2026 · **My role:** reporting the issue and checking the fix

## Problem

I asked Jarvis through Telegram to add a task. The assistant replied, but no card appeared in Trello. The reply did not claim that the card had been saved, yet the request was not carried out: it had been handled as an ordinary conversation instead of a task command.

## Example steps

The wording below is a neutral example, not the original message.

1. In Telegram, send: "Add a task for tomorrow: prepare the demo."
2. When asked, choose the task group.
3. Compare the assistant's reply with the Trello board.

**Expected:** the assistant asks for anything missing, creates one card in the right group with the right date and confirms what was saved. If it cannot save the card, it says so clearly.

**Actual:** a text reply and no card on the board.

## Fix and retest

I reported the mismatch with examples from use. AI coding agents found the cause, changed how such requests are handled and added regression tests. After the fix, the record shows one card in the intended group with the intended date.

Separately, I added and completed a test task through Telegram and by phone, and checked that the completed task no longer appeared in the next daily plan.

## What I take from it

When an assistant or an integration says something, I check the result in the connected tool. A reply, a draft and a saved task are three different outcomes.
