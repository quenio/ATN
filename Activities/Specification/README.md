# ATN Activities: Specification

Using ATN to specify required constraints, behaviors and invariants that serve as primary inputs to design and testing.

This activity can be part of the Assurance workflow, the Engineering workflow, and the Requirements workflow.

## ATN Use in Specification

Specification uses ATN in two ways within the [Assurance workflow](../../Workflows/Assurance), the [Engineering workflow](../../Workflows/Engineering), and the [Requirements workflow](../../Workflows/Requirements):

- as input, by using ATN concepts, models, and source requirements to define required constraints, behaviors, and invariants precisely
- as output, by contributing ATN specifications that serve as primary inputs to downstream activities including Design and Testing

## Tooling

- `./atn spec <markdown_file.md>` generates `<markdown_file.spec.md>` from a Markdown requirements document.

## Examples

- [DocumentApproval](../../Examples/Processes/DocumentApproval): a small `atn spec` example and test based on a short natural-language requirements document for a document approval workflow.
- [ModelContextProtocol](../../Examples/Protocols/ModelContextProtocol): a larger `atn spec` example and test based on the Model Context Protocol specification, including a local source copy and a generated ATN version under [Protocols](../../Examples/Protocols).

## Sources

Representative sources include:

- [NASA Systems Engineering Handbook](https://www.nasa.gov/wp-content/uploads/2018/09/nasa_systems_engineering_handbook_0.pdf), which identifies `Technical Requirements Definition Process` as a distinct activity feeding later design and realization.
- [DoD Systems Engineering Guidebook](https://www.cto.mil/wp-content/uploads/2024/05/SE-Guidebook-Feb2022.pdf), which identifies `Stakeholder Requirements Definition Process` and `Requirements Analysis Process` as core technical processes.
- [SEBoK: Applying Life Cycle Processes](https://sebokwiki.org/wiki/Applying_Life_Cycle_Processes), which discusses stakeholder needs, concept definition, and `system requirements definition` as linked life-cycle processes.
