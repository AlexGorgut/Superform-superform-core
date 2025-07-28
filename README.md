# Superform Core Audit Findings Summary

This repository contains security audit findings for the Superform Core project, a cross-chain yield protocol. The audit identified one vulnerability during the security assessment.

## Findings

## 1. Merkle Leaf Mismatch in SuperDestinationValidator Leads to Rejection of README-Compliant Messages
# [Info](https://cantina.xyz/competitions/ba62fa4e-f933-4eec-b9ac-868325f4a694) Severity
The `SuperDestinationValidator.sol` contract calculates Merkle leaves using a structure that omits the adapter address and uses global signature expiry, which mismatches the README.md's implied leaf structure. This discrepancy causes valid messages constructed per README documentation to be rejected with an `INVALID_PROOF` error.

- **Impact**: Denial of service for messages following README documentation, forcing users to deviate from documented behavior.
- **Root Cause**: Mismatch between documented leaf structure and validator's internal leaf calculation implementation.

## Summary Statistics
- **Total Findings**: 1
- **High Severity Findings**: 0
- **Medium Severity Findings**: 0  
- **Low Severity Findings**: 0
- **Info Severity Findings**: 1
