# Short Block-length Codes for Ultra-Reliable Low Latency Communications (URLLC)

This repository presents our research on short block-length codes tailored for Ultra-Reliable Low Latency Communications (URLLC), a critical component of 5G and future wireless networks. The study explores coding schemes that balance the trade-off between reliability and latency, which is essential for time-sensitive, mission-critical applications.

---

## Research Team

- Harshit Soni (ID: 202211027)  
- Hridyansh Sharma (ID: 202211029)  
- Shreyas Makwana (ID: 202211046)  
- Daksh Mehta (ID: 202211049)

---

## Motivation

URLLC requires:

- Reliability up to 1–10⁻⁹  
- Latency as low as 0.1 milliseconds

This introduces a fundamental trade-off:

- Short packets reduce latency but suffer from reduced coding gain  
- Strong codes improve reliability but increase decoding delay

Target applications include:

- Factory automation  
- Tele-surgery  
- Smart grids  
- Tactile internet

---

## Research Objectives

This project investigates short block-length codes under strict URLLC conditions, focusing on:

1. Performance relative to the Normal Approximation (NA) benchmark  
2. Trade-offs between complexity and performance  
3. Reliability at ultra-short code lengths  
4. Rate adaptability under varying SNR conditions

---

## Key Findings

### 1. Performance Comparison (Reliability)

For codeword length N = 128, rate R = 1/2, using BI-AWGN channel and Maximum Likelihood Decoding (MLD):

| Code Type          | BLER = 10⁻⁷ Gap to NA | Notes |
|--------------------|------------------------|-------|
| Extended BCH       | ~0.1 dB                | Closest to NA benchmark |
| TB-CC (m = 14)     | ~0.3 dB                | Reliable at BLER = 10⁻⁵ but degrades at lower BLER |
| Performance Order  | eBCH > TB-CC > LDPC (F₂₅₆) > Polar+CRC > LDPC (binary) > Turbo |

---

### 2. Rate vs. SNR Performance

For codeword length N = 128, BLER = 10⁻⁴, over BI-AWGN channel:

- BCH codes with Order-5 OSD: Closest to Normal Approximation across all SNRs  
- Polar codes with CA-SCL (L = 32): Significantly better than L = 4  
- eMBB LDPC codes: Low complexity and better than CA-Polar (L = 4)

---

### 3. Complexity vs. Performance Trade-off

For N = 128, R = 1/2, BLER = 10⁻⁴:

| Code Type               | Gap to NA | Complexity (operations/bit) |
|--------------------------|-----------|------------------------------|
| TB-CC (m = 14)           | 0.3 dB    | ~10⁷                         |
| eBCH with OSD-5          | 0.1 dB    | ~10⁵                         |
| Polar with CA-SCL (L=32) | 0.5 dB    | ~10³                         |
| LDPC with BP             | 0.8 dB    | ~10³                         |

Conclusion: Polar codes provide the best balance between decoding complexity and performance for URLLC applications.

---

## Future Research Directions

1. Low-Complexity ML-like Decoders  
   - Optimized Order-Statistic Decoding (OSD) with bounded complexity  
   - Segmented and sufficiently conditioned OSD techniques

2. Self-Adaptive Coding Schemes  
   - Avoid explicit channel estimation  
   - Enable real-time rate adaptation without CQI feedback

3. Space-Frequency Channel Coding  
   - Utilize spatial diversity instead of multiplexing  
   - Design for enhanced reliability in multi-dimensional channels

---
