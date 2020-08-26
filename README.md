# WorkOS Network

The WorkOS Network platform is an extension of Monday.com

The Monday.com platform is a flexible project and team management system. Allowing businesses to craft unique business flows and systems

## Overview

The Monday WorkOS comes with a core "Dashboard System Schema": Pulses, Boards, Users, Team and a few other important information tracking features.

WorkOS Network extends those core features. Connecting to other data sources and business data.

Why you might ask? Monday WorkOS connects natively to other popular platforms like Twilio, MailChimp, Gmail, Github, Shopify to enable automated pulse creation and notifcations. But... sometimes you don't want to just create new tasks, items or reminders.

# Architecture

WorkOS Network is a fullstack application - organized in 3 major folder structures.

- Administration
- Backend
- Frontend

#### Administration

- workos-network-saas (kubernetes/docker/node/express)
  - server (node/express/postgress)
  - server-router (node/express)
  - proxy (docker/nginx)
- workos-network-site (react/webpack via next.js)
- workos-network-tools (devloper utility/helper scripts)

#### Backend

- workos-graphql-monday (DockerNode/Express/GraphQL)
- workos-network-authentication DockerNode/Express/GraphQL)
- workos-network-screens (Docker/NGINX)

#### Frontend

- workos-network-widgets (Next.js/Lerna)
- workos-network-views (Next.js/Lerna)

### Testing

- workos-network-cli

### Saas - WorkOS Network (workos-network-saas)

The `WorkOS Network SaaS` manages user authentication and service management.

- Monday 0Auth Integration
- Role Based Permissions
- Manages Kubernetes Cluster

## Why

The `WorkOS Network SaaS` enable users to easily extend Monday.com with flexible data management features. With the recent announcement of the WorkOS Marketplace.

Users register to WorkOS Network with valid **Monday Credentials** and create a new Team WorkOS Hub. The hub (hasura kubernetes instance) is a multiple purpose service, accessible to various skill levels.

The hub (as of now) can be used by advanced data manager and also general application managers. The hub includes advanced data management capalities managed via a backend interface (manually builde data structures and define new relationships). General application managers can select from a "catalog" system to enable pre-built extensions.

#### Data Administrator

- Database (postgres)
- Schema Sticher (Graphql)

#### Application Manager

- Extension Catalog
- Automdated Setup

### Website - WorkOS Network (workos-network-site)

The WorkOS Network Website is a standard Frontend React application. Monday Users can login, setup a WorkOS Network Hub, invite team members and utilize a collection of existing view and widgets (technically referred to as screens) to extend the Monday Dashboard system.

### Why

An enjoyable user experience.

- Team Setup
- Service Management

## Backend

### Hub/Monday Bridge - (workos-graphql-monday)

The `Monday Graphql Stich` module is lightweight Authentication and GraphQL router, brigding the WorkOS Hub (http://project.workos.network) and Monday API URL (http://api.monday.com/v2).

#### Why

The WorkOS Network Hub forwards a signed JWT issued via the. The bridge validates the JWT and requests a one-time access token, forwarding the request to Monday.com API V2 (GraphQL) endpoint.
