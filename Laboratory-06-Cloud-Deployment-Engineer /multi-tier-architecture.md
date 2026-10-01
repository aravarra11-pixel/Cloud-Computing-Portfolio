# Multi-Tier Architecture

## Overview
A two-tier architecture splits an application into a presentation/application tier
and a data tier that communicate over a network instead of running in one process.

## The Web/Application Tier
Role: serves the Nextcloud user interface, handles incoming HTTP requests, runs
the application logic, and authenticates users. Holds no authoritative data of
its own — restarting it loses nothing.

## The Database Tier
Role: durable storage for user accounts, password hashes, file metadata, shares,
and app configuration. Reached only through the application tier, never directly
by the browser.

## Why Separate Them?
Independent scaling and patching, limiting blast radius if one tier is
compromised, smaller purpose-built images, and easier backup/replacement.


