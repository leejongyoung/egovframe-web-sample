# egovframe-web-sample: project context

## Role and maintenance boundary

A Spring-based simple bulletin-board web example with list and registration pages. Preserve sample controller routes, form behavior, JSP rendering, and mapper/database interfaces.
This card reflects source inspection at adoption; it does not certify runtime behavior.

## Public entry points and evidence

- `README.md`: simple board example, JDK 17, Jakarta EE 9, Servlet 5.0, Spring Framework 6.2.11, and Eclipse Run on Server instructions.
- `pom.xml`: WAR packaging, eGovFrame web-config parent, Selenium dependency, and Surefire includes `**/*Test.java`.
- `.github/workflows/maven.yml`: JDK 17 and `mvn -B package --file pom.xml -Dmaven.test.skip=true`.
- `src/test/`: service/mapper/controller/JSP regressions; `TestEgovSampleControllerTestSelenium.java` is outside the configured test suffix pattern.

## Build and verification entry points

CI packages with `mvn -B package --file pom.xml -Dmaven.test.skip=true`; it does not prove
that any tests ran. For a future fix select a relevant test with `mvn -Dtest=ClassName test`
and inspect its result and prerequisites. Before claiming browser coverage, explicitly
confirm test discovery and exercise the running sample with the required browser and DB.
Use README Eclipse Run on Server instructions for runtime validation. The Selenium discovery
issue (fork issue #1) is recorded as context and remains unchanged.

## Environment and evidence limits

A servlet runtime, database setup and browser environment can be required for integration
checks. Keep this repository a small example rather than imposing an unverified application
architecture or adding feature policy during tooling adoption.
No application build, test suite, formatter, device test, or external service was run for this
workflow-only adoption. A Spec Kit CLI/status and isolated scaffold smoke validate the tooling
only. No CodeGraph index was present in the adoption workspace; targeted file listing and
exact text inspection supplied the evidence, without installing an indexer.

## Upstream and submission baseline

Upstream: [eGovFramework/egovframe-web-sample](https://github.com/eGovFramework/egovframe-web-sample). Fetch the actual upstream default branch
and record its exact SHA before preparing `upstream-submit`; do not infer the baseline from
fork work. Preserve an existing submission branch or open PR. Adoption changes are pushed
only to fork `work`; an absent `upstream-submit` is created from the fetched upstream SHA
without adoption commits, as a separate submission baseline.
The [constitution](constitution.md) is the policy source for domain cards, verification, and
work-only artifact isolation. Native OMP commands are in `.omp/commands/`; the bundled bug
workflow provides assess, fix, and test stages. No application fix or PR is part of
this adoption.
