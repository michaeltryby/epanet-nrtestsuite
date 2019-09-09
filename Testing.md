<!---
   Testing.md

   Created: Sept 6, 2019
   Updated: Later

   Author: Michael E. Tryby
           US EPA - ORD/NRMRL
--->

## Regression Testing SOPs


### Adding Tests

  1. Create a test configuration json file using test-config script.

  2. Add the input and configuration files to the repo.

  3. Generate new test artifacts.

  4. Add new test artifacts to the benchmark archive.

  5. Update the release with the new benchmark archive.


### Updating Rolling Benchmark

  1. Retrieve SUT Benchmark artifact from Appveyor CI.

  2. Inspect SUT Benchmark for anomalous results. If the results checkout then
     proceed to Step 3 otherwise do not merge the changes. Instead create an
     issue describing the problem.

  3. Create a new release in the epanet-nrtests repo

  4. Attach SUT Benchmark to the new release.

  5. Determine BUILD_ID from SUT Benchmark manifest.

  6. Update REF_BUILD_ID variables in epanet appveyor.yml file (this will
     trigger a new build on Appveyor CI)

  7. Check that nrtests are passing on Appveyor CI.

  8. Merge the PR. The SUT Benchmark is now the new REF Benchmark.