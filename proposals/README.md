# Julia Enhancement Proposals (Juleps) README   

Juleps represent a formal process for proposing substantial changes to Julia.

A proposed change should be considered "substantial" in order for a Julep to be considered. A "substantial" change is generally defined as any change that will introduce or significantly modify: 

- Language features (syntax, semantics, interfaces)
- Core components (standard library)
- Project infrastructure (CI/CD, documentation, licensing) 

Examples of changes that are not substantial may include:
- Bux fixes
- Minor documentation corrections or improvements
- "Local" performance improvements (those that affect specific contexts)
- Changes that will go unoticed by a significant majority of Julia users  

Note that these criteria are both intentionally ambiguous and non-exhaustive, and are meant to provide a general understanding for when a Julep is necessary. It is important to think of a Julep as a public point of discussion on extensive contributions to the Julia language and ecosystem.  

## Contributing

1. Consult [Julep 0001 - Julep Process and Guideline](./juleps/0001-julep_process_and_guideline/0001-julep_process_and_guideline.md)
2. Fork the [Julia repository](https://github.com/JuliaLang/julia.git)
3. Place a copy of thethe [template directory](./TEMPLATE/) under the `juleps` directory and rename both the directory and file to include the next unassigned Julep number (subject to change) and proposal title
4. Create the draft public document for your Julep, along with any assets 
5. Submit an RFC pull request detailing your proposal for feedback with the title `[Julep] RFC: title here`
6. If approved, change the Julep number if needed and request to merge
