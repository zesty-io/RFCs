# RFC 0014 - Design System

## Summary

At a certain point in a project, consistency across components becomes hard to maintain and can lead to a bad or confusing user experience. The goal of a design system is to minimize the need for individual developers to be tasked with styling the ui as functionality is added. “Design systems provide a convenient, centralized, and evolving map of a brand’s known product territories with directional pointers to help you explore new regions.” –Chris Messina, tech evangelist and former Developer Experience Lead at Uber.

## Design System Nomenclature - atomic design

**Atom**: The smallest possible component.

**Molecule**: The joining of two or more components to create another component (eg button + text input = search).

**Organisms**: Organisms are relatively complex UI components composed of groups of molecules and/or atoms and/or other organisms. These organisms form distinct sections of an interface.

**Templates**: Templates are page-level objects that place components into a layout and articulate the design’s underlying content structure.

**Pages**: Straightforward enough, full vies that include the use of Templates, and Organisms.

## Design System

1. **Initial Generation:** Creation of all necessary Atoms and Molecules, adhering to a particular design style including color palate, typography, sizing and behavior.

2. **Usage:** All front end developers will have access via an NPM package, and use only items from the design system package when implementing features, or new views. 
