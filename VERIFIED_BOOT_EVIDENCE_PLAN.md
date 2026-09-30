# Verified-Boot Evidence Plan

## Current state
Verified-boot evidence is PENDING. Integration, checksums, successful boot, or signed source are not substitutes for verified-boot proof.

## Phase 1: Artifact identity
Record image SHA256, source commit, ChromiumOS manifest hash, Kernel pin, and immutable final artifact.

## Phase 2: Signing provenance
Identify target signing configuration, public verification material, signing-tool versions, and signing records. Never commit private signing material.

## Phase 3: Boot-chain evidence
1. Identify firmware/root-of-trust boundary.
2. Identify verified payload and signature/checking stage.
3. Capture verification result from the actual target path.
4. Where safely supported, test rejection of an altered artifact.
5. Bind every result to the exact artifact hash.

## Phase 4: Runtime correlation
Boot the verified artifact, record runtime identity, confirm it matches the verified artifact, then run the Runtime Validation Suite against that identity.

## Required evidence
- Artifact SHA256
- Source commit
- Manifest hash
- Kernel pin
- Signing configuration
- Public verification material
- Boot-chain verification output
- Safe invalid-artifact rejection evidence
- Runtime identity
- Environment and timestamps

## Acceptance
Verified boot is accepted only when evidence demonstrates a cryptographic verification chain from the target trusted boot boundary to the exact tested artifact.

A bootable artifact is not automatically verified-boot evidenced. A signed artifact is not automatically verified-boot evidenced. These distinctions remain mandatory for diligence.
