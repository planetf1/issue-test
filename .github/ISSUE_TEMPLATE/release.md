<!-- SPDX-License-Identifier: CC-BY-4.0 -->
<!-- Copyright Contributors to the Egeria project. -->
---
name: Release
about: Template for Tracking a new release
title: Release [x.y]
labels: release
assignees: planetf1

Create release x.y :

Prior to the release work
- [ ] slack post advising of upcoming release & linking to issue
- [ ] advance warning in developer/community call
- [ ] final agreement to start branch in team call & identification of outstanding issues
- [ ] Agree required updates/versions for additional repos including egeria-ui, egeria-reactui, connectors etc

Branching & Correcting versions
- [ ] Create branch
- [ ] Reassign any issues not being worked on to the next release
- [ ] Update version for master (ie x.y-SNAPSHOT > x.y+1-SNAPSHOT)
- [ ] Update version for branch (ie x.y-SNAPSHOT -> x.y)

Final updates to the release
- [ ] Ensure any remaining fixes are merged into branch
- [ ] Remove release notes from branch
- [ ] update release notes & rename
- [ ] ensure any fixes ported to master

Updating the React UI (as this is part of the notebook test). Note egeria-ui is out of scope other than inclusion of current release
- [ ] Branch React UI (as with all items under Branching/correcting versions for egeria itself

Updating the Helm Charts & docker-compose
- [ ] checker correct docker images are on dockerhub (these are built by the 'merge' build of a release)
- [ ] Update image versions for compose (egeria repo) 
- [ ] update image versions for helm charts (egeria-charts repo)

Final tests
- [ ] Check swagger doc renders (no regressions)
- [ ] Verify odpi-egeria-lab chart (pods active/ready)
- [ ] Verify egeria-base chart (pods active/ready)
- [ ] Verify docker compose (active/ready)
- [ ] Check notebooks (config, start, data catalog at a minimum)
- [ ] Check polymer UI (only possible to check it runs - no demo scenario for more)
- [ ] Check React UI (rex, tex, glossary author)
- [ ] CTS - graph
- [ ] CTS - inmemory

Final build and publish
- [ ] Run 'release' pipeline on branch to push candidates to oss.sonatype.org
- [ ] 'close' staging repo & Validate artifacts ok (number, structure, validations) on oss.sonatype.org
- [ ] Run 'release' pipeline on egeria-reactui & validate artifacts
- [ ] Create final github releases for egeria (use release notes from master as text)
- [ ] Create final github release for egeria-ui
- [ ] Close repo on oss.sonatype.org (once updated) for egeria, release
- [ ] Close repo on oss.sonatype.org for egeria-react ui
- [ ] Check 'release' repo on oss.sonatype.org has artifacts
- [ ] Publish that release is now shipped via slack #egeria-announce
- [ ] Additional posts to social media
- [ ] Communicate to other repo owners ie for connectors so that they can be rebuilt/shipped as needed


Target Date:
---