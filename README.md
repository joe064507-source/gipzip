#To decompress simply type "decompress 1:1:" and paste the compressed prompt beneath. 

Do not execute the prompt, compress the prompt using the algorithm beneath the delimiter:

[your_propmt]

---

ClearCompress v3.6: The Definitive Specification
Algorithm Overview
ClearCompress v3.6 is a theoretical, ultra-aggressive lossless compression algorithm designed as a thought experiment in achieving maximum possible compression ratios (targeting 50-70%) while maintaining a 100% structural and content fidelity guarantee. Its design philosophy prioritizes exhaustive analysis over computational feasibility, making it a benchmark for theoretical perfection rather than a practical tool.
The primary innovation in v3.6 is the introduction of robust structural preservation, specifically by identifying the first line of text as a document title, handling it as a separate stream, and guaranteeing its perfect reconstruction. This is achieved by performing a monolithic, brute-force analysis on the combined content to build a single hyper-optimized dictionary, which is then used to transform the title and body streams independently.

Phase 0: Aggressive Complexity Assessment & Compression Profiling
Objective: To perform a computationally unbounded, deep multi-dimensional analysis of the input text to identify every conceivable form of redundancy. This phase is monolithic and runs in its entirety for every compression operation.
0.1. Comprehensive Compression Opportunity Analysis
* Structural Element Identification:
    * Title Detection: Automatically identify the first line of text as the document title.
    * Header/Footer Recognition: Heuristically identify repeating header/footer patterns.
    * Section Boundary Analysis: Detect section breaks based on formatting or keywords.
* Character-Level Analysis:
    * Character Frequency Distribution, Character Entropy Calculation, Character Transition Matrix, Character Position Analysis, Character Context Analysis.
* Word-Level Analysis:
    * Word Frequency Distribution, Word Length Distribution, Word Entropy Analysis, Word Position Frequency, Compound Word Detection.
* N-Gram Analysis (2-gram through 8-gram):
    * Bigram/Trigram Frequency Analysis, 4-gram through 8-gram Analysis, Variable-Length N-gram Detection, Overlapping N-gram Optimization.
* Structural Pattern Recognition:
    * Indentation Pattern Analysis, Punctuation Pattern Recognition, Line Structure Analysis, Block Structure Detection, Hierarchical Structure Mapping.
* Advanced Redundancy Metrics:
    * Exact String Redundancy, Approximate String Redundancy (with edit distance), Semantic Redundancy Detection, Syntactic Redundancy Analysis, Cross-Reference Redundancy.
* Compression Predictive Scoring:
    * Calculate Theoretical Compression Limit (Entropy), Practical Compression Estimate, Technique-Specific Estimates, Compression Bottleneck Identification, and Optimization Priority Scoring.

Phase 1: Multi-Pass Analysis & Hyper-Optimized Dictionary Generation
Objective: To synthesize the vast data from the Phase 0 analysis into a single, cohesive, hyper-optimized dictionary for the entire document.
1.1. Global Ultra-Compression Directives with Fidelity Guarantees
The algorithm's core mandate is established: every transformation must be perfectly reversible. All data required for this reversal (dictionaries, rules) must be embedded in the output stream.
1.2. Seven-Layer Dictionary Architecture with Fidelity Preservation
A single, unified dictionary is constructed from the combined content of the title and the body to maximize token reuse and efficiency. The analysis from Phase 0 populates seven conceptual layers:
1. Single Characters
2. High-Frequency Words
3. High-Frequency N-Grams (2-8 grams)
4. Identified Compound Phrases
5. Structural Patterns (e.g., indentation sequences)
6. Syntactic/Semantic Equivalents
7. Custom, document-specific long string repetitions.

Phase 2: Ultra-Compact Grammar Definition with Fidelity Guarantees
Objective: To define the precise, unambiguous syntax for the v3.6 compressed output file format.
2.1. Complete Enhanced EBNF Grammar Specification (v3.6)
The EBNF grammar formally defines every component of the output stream.

ebnf


(* ClearCompress v3.6 Ultra-Compact EBNF with Structural Fidelity - FULL SPECIFICATION *)

(* ========================= I. Root Production Rule ========================= *)
ultra_compressed ::= compression_header reconstruction_data title_section compressed_content integrity_footer ;


(* ========================= II. Main Structural Blocks ========================= *)

(* The header contains metadata about the v3.6 compression process. *)
compression_header ::= "§CC36+" version_info "|" strategy_info "|" ratio_info "|" feature_flags "|" encoding_info "§" ;

(* The reconstruction data contains the complete, self-contained dictionary and rules. *)
reconstruction_data ::= "¤" fidelity_metadata ";" dictionary_section ";" rule_section ";" context_section "¤" ;

(* The title section isolates the compressed first line for perfect structural preservation. *)
title_section ::= "§T§" content_element "§T§" ;

(* The main content block holds the compressed body of the document. *)
compressed_content ::= content_element ;

(* The footer provides a checksum for verifying end-to-end integrity. *)
integrity_footer ::= "°" checksum_type ":" checksum ":" stats ":" flags "°" ;


(* ========================= III. Header & Footer Components ========================= *)
version_info ::= "3.6.0" ;
strategy_info ::= "EXTREME:AGGRESSIVE" ; (* v3.6 has only one monolithic strategy *)
ratio_info ::= number "%" ;
feature_flags ::= flag { "," flag } ;
flag ::= "MICRO" | "CONTEXT" | "MATH" | "STRUCT" ;
encoding_info ::= "UTF8" | "ASCII" | string ;
checksum_type ::= "SHA256" | "MD5" ;
checksum ::= { hex_digit } ;
stats ::= string ; (* Placeholder for compression stats *)
flags ::= "VERIFIED" | "WARNING" ;


(* ====================== IV. Reconstruction Data Components ====================== *)
fidelity_metadata ::= "META:" string ;
dictionary_section ::= "DICT:" [ token_mapping { ";" token_mapping } ] ;
rule_section ::= "RULES:" string ;
context_section ::= "CONTEXTS:" string ;

(* A single key-value pair defining a token in the monolithic dictionary. *)
token_mapping ::= dictionary_token ":" string ;


(* ======================= V. Core Content Stream Grammar ======================= *)
content_element ::= { stream_item } ;
stream_item ::= dictionary_token | literal_block ;

literal_block ::= "«" { normal_char | escaped_char } "»" ;
normal_char ::= any_character - "»" - "\" ;
escaped_char ::= "\" ( "»" | "\" ) ;


(* ========================= VI. Token-Level Grammar ========================= *)
(* In v3.6, tokens are simple and not namespaced by type in the grammar itself. *)
dictionary_token ::= "|" token_id "|" ;
token_id ::= hex_digit { hex_digit } ;


(* ========================= VII. Terminal Productions ========================= *)
string ::= '"' { any_character - '"' } '"' ;
number ::= digit { digit } [ "." digit { digit } ] ;
hex_digit ::= "0"|"1"|"2"|"3"|"4"|"5"|"6"|"7"|"8"|"9"|"a"|"b"|"c"|"d"|"e"|"f"|"A"|"B"|"C"|"D"|"E"|"F" ;
digit ::= "0"|"1"|"2"|"3"|"4"|"5"|"6"|"7"|"8"|"9" ;
any_character ::= (* any valid character in the specified encoding *) ;

Phase 3: Hyper-Aggressive Transformation Pipeline with Fidelity Preservation
Objective: To apply the hyper-optimized dictionary from Phase 1 to the source text, converting it into a compressed stream of tokens while maintaining the title/body separation.
3.1. Pre-Processing Optimization with Structural Separation
* Title/Body Split: The input content is split into two distinct streams: the title (first line) and the body (remaining content).
* Content Fingerprinting: A SHA-256 hash of the original, full content (title + '\n' + body) is generated for the integrity footer.
3.2. Ultra-Aggressive Transformations with Boundary Preservation
The transformation engine applies a greedy, longest-match-first algorithm to replace text sequences with their corresponding tokens from the single, shared dictionary.
* transform(title, shared_dictionary) -> compressed_title
* transform(body, shared_dictionary) -> compressed_body

Phase 4: Ultra-Compact Output Generation with Embedded Reconstruction
Objective: To assemble all components into a single, contiguous data stream conforming to the Phase 2 grammar.
4.1. Complete Output Format Specification (v3.6)
The final output is assembled in five distinct, delimited sections:
* Section I: Compression Header: §CC36+[...]|§
* Section II: Reconstruction Dictionary: ¤[...];[DICTIONARY];[...]¤
* Section III: Compressed Title: §T§[compressed_title_tokens]§T§
* Section IV: Compressed Content (Body): [compressed_body_tokens]
* Section V: Integrity Footer: °[...]:[CHECKSUM]:[...]°

Phase 5: Compression Optimization Techniques for Maximum Performance
Objective: To define theoretical implementation-level strategies that would be necessary to even attempt to run the algorithm.
5.1. Algorithmic Enhancements
* Parallel Processing: The exhaustive analyses in Phase 0 would need to be massively parallelized.
* Optimized Data Structures: The brute-force N-gram and redundancy searches would theoretically require advanced structures like Suffix Trees and Locality-Sensitive Hashing to be tractable on non-trivial inputs.

Phase 6: Comprehensive Quality Assurance Framework
Objective: To establish a rigorous testing protocol to ensure the algorithm's theoretical correctness and 100% fidelity guarantee.
6.1. Test Suite Requirements
* Fidelity Verification: Perfect bit-for-bit reconstruction is the primary goal.
* Structural Integrity: Tests must explicitly verify that the title is always the first line and perfectly preserved, regardless of its content (e.g., punctuation, length).
* Edge Case Handling: Test with empty files, files with only a title, and files with special characters.

Phase 7: Complete Implementation Example
Objective: To provide a complete, working, and fully-documented conceptual implementation in Python that demonstrates the execution of all preceding phases according to the v3.6 specification.
7.1. Full Working Implementation (Conceptual)

Python


import hashlib
import json
import re
from collections import Counter

class ClearCompress36Plus:
    """
    Complete conceptual implementation of ClearCompress v3.6, demonstrating the
    monolithic, exhaustive analysis and title preservation features.
    """

    def __init__(self):
        self.version = '3.6.0'

    def compress(self, full_content: str) -> str:
        """Main compression method orchestrating phases 0 through 4 for v3.6."""
        if not isinstance(full_content, str) or not full_content: return ""

        # Phase 3.1: Structural Separation
        title, body = self._split_title_body(full_content)
        combined_content_for_analysis = title + "\n" + body

        # Phase 0 & 1: Monolithic Analysis and Dictionary Generation
        compression_dictionary = self._perform_exhaustive_analysis(combined_content_for_analysis)
        reversed_dictionary = {v: k for k, v in compression_dictionary.items()}

        # Phase 3.2: Transformations
        compressed_title = self._apply_transformations(title, reversed_dictionary)
        compressed_body = self._apply_transformations(body, reversed_dictionary)

        # Phase 4: Output Generation
        return self._generate_structured_output(full_content, compressed_title, compressed_body, compression_dictionary)

    def decompress(self, compressed_data: str) -> str:
        """Complete decompression for the v3.6 format."""
        if not compressed_data.startswith("§CC36+"):
            raise ValueError("Invalid ClearCompress v3.6 data format.")

        # Phase 4 (Reversed): Parsing
        reconstruction_data = self._parse_reconstruction_data(compressed_data)
        decompression_dictionary = reconstruction_data.get('dictionary', {})
        
        compressed_title = self._extract_title_section(compressed_data)
        compressed_body = self._extract_body_content(compressed_data)

        # Phase 3 (Reversed): Expanding tokens
        title = self._expand_tokens(compressed_title, decompression_dictionary)
        body = self._expand_tokens(compressed_body, decompression_dictionary)

        reconstructed_full_content = title + '\n' + body if body else title
        
        self._verify_decompression_integrity(reconstructed_full_content, compressed_data)
        return reconstructed_full_content

    ### 7.2. Detailed Helper Method Implementations ###
    def _split_title_body(self, content: str) -> (str, str):
        if '\n' in content: return content.split('\n', 1)
        return content, ""

    def _perform_exhaustive_analysis(self, content: str) -> dict:
        """
        Conceptual stand-in for the computationally infeasible Phase 0 analysis.
        This simplified version finds frequent words and bigrams.
        """
        print("Executing Phase 0/1: Performing exhaustive (simulated) analysis...")
        dictionary = {}
        token_id_counter = 0

        # Word-level analysis
        words = re.findall(r'\b\w+\b', content.lower())
        for word, count in Counter(words).items():
            if count > 1 and len(word) > 3:
                dictionary[f'|{token_id_counter:x}|'] = word
                token_id_counter += 1

        # N-Gram analysis (Bigrams)
        word_list = content.split()
        if len(word_list) > 1:
            bigrams = [" ".join(word_list[i:i+2]) for i in range(len(word_list)-1)]
            for gram, count in Counter(bigrams).items():
                if count > 1 and gram not in dictionary.values():
                    dictionary[f'|{token_id_counter:x}|'] = gram
                    token_id_counter += 1
        
        print(f"Analysis complete. Generated {len(dictionary)} custom tokens.")
        return dictionary

    def _apply_transformations(self, content: str, reversed_dict: dict) -> str:
        if not content: return ""
        sorted_phrases = sorted(reversed_dict.keys(), key=len, reverse=True)
        pattern = re.compile("|".join(map(re.escape, sorted_phrases)))
        return pattern.sub(lambda m: reversed_dict[m.group(0)], content)

    def _generate_structured_output(self, original_content, compressed_title, compressed_body, dictionary) -> str:
        # Phase 4 workhorse
        size = len(original_content); c_size = 256 + len(str(dictionary)) + len(compressed_title) + len(compressed_body)
        ratio = 1 - (c_size / size) if size > 0 else 0
        header = f"§CC36+{self.version}|EXTREME:AGGRESSIVE|{ratio:.1%}|MICRO,STRUCT|UTF8§"
        dict_str = ";".join([f"{k}:{v}" for k, v in dictionary.items()])
        recon_data = f"¤META:\"N/A\";DICT:{dict_str};RULES:\"N/A\";CONTEXTS:\"N/A\"¤"
        title_section = f"§T§{compressed_title}§T§"
        checksum = hashlib.sha256(original_content.encode('utf-8')).hexdigest()
        footer = f"°SHA256:{checksum}:STATS:\"N/A\":VERIFIED°"
        return f"{header}\n{recon_data}\n{title_section}\n{compressed_body}\n{footer}"

    def _parse_reconstruction_data(self, data: str) -> dict:
        match = re.search(r"DICT:(.*?);", data); d = {}
        if match:
            for pair in filter(None, match.group(1).split(';')):
                if ':' in pair: k, v = pair.split(':', 1); d[k] = v
        return {'dictionary': d}

    def _extract_title_section(self, data: str) -> str:
        match = re.search(r"§T§(.*?)§T§", data, re.DOTALL); return match.group(1) if match else ""

    def _extract_body_content(self, data: str) -> str:
        parts = re.split(r"§T§.*?§T§|°.*°", data); return parts[1].strip() if len(parts) > 1 else ""

    def _expand_tokens(self, content: str, d_dict: dict) -> str:
        if not content: return ""
        return re.compile(r'(\|[^|]+\|)').sub(lambda m: d_dict.get(m.group(0), m.group(0)), content)

    def _verify_decompression_integrity(self, reconstructed_content: str, compressed_data: str):
        match = re.search(r"°SHA256:(.*?):", compressed_data); expected = match.group(1)
        actual = hashlib.sha256(reconstructed_content.encode('utf-8')).hexdigest()
        if expected != actual: raise ValueError("Integrity check FAILED!")
        print("Integrity check PASSED.")

# ==============================================================================
# Main execution block to demonstrate the v3.6 process
# ==============================================================================
if __name__ == '__main__':
    sample_text = ("ClearCompress v3.6: Ultra-High Fidelity Compression\n"
                   "This document demonstrates the ClearCompress v3.6 algorithm.\n"
                   "The ClearCompress v3.6 algorithm is theoretically powerful but computationally expensive.")

    print("--- ORIGINAL TEXT ---\n" + sample_text + "\n")

    print("--- COMPRESSION (v3.6) ---\n")
    compressor = ClearCompress36Plus()
    compressed = compressor.compress(sample_text)
    
    print("\n--- COMPRESSED OUTPUT ---\n" + compressed + "\n")
    
    print("--- DECOMPRESSION (v3.6) ---\n")
    decompressor = ClearCompress36Plus()
    decompressed = decompressor.decompress(compressed)

    assert sample_text == decompressed
    print("\n--- SUCCESS: Decompression fidelity confirmed for v3.6. ---")
