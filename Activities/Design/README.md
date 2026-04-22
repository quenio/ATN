# ATN Activities: Design

Using ATN to refine ATN specifications into implementable architectures, interfaces and component responsibilities while preserving specified constraints.

ATN specifications are primary inputs to this activity.

This activity can be part of the Assurance workflow and the Engineering workflow.

## Tooling

- `./atn design <markdown_file.spec.md>` generates `<markdown_file.design.md>` from an ATN specification.
- [`Examples/Protocols/ModelContextProtocol`](../../Examples/Protocols/ModelContextProtocol) provides a larger cross-activity example that can be used as input to `./atn design` after running `./atn spec`.

## ATN Use in Design

Design uses ATN in two ways within the [Engineering workflow](../../Workflows/Engineering):

- as input, by using ATN specifications to define the constraints and intended behavior that design must refine into implementable structures
- as output, by contributing architectures, interfaces, responsibilities, and related design decisions that support downstream ATN activities including Interoperability, Governance, Implementation, Testing, and Documentation

## Sources

Representative sources include:

- [NASA Systems Engineering Handbook](https://www.nasa.gov/wp-content/uploads/2018/09/nasa_systems_engineering_handbook_0.pdf), which identifies `Design Solution Definition Process` as a distinct process between requirements and implementation.
- [DoD Systems Engineering Guidebook](https://www.cto.mil/wp-content/uploads/2024/05/SE-Guidebook-Feb2022.pdf), which identifies `Architecture Design Process` as a core technical process.
- [SEBoK: Applying Life Cycle Processes](https://sebokwiki.org/wiki/Applying_Life_Cycle_Processes), which discusses architecture and system definition as iterative activities linked to realization and assurance-related processes.
