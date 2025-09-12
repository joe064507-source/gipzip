# gipzip
A compression tool for LLMs.

Paste the prompt with the prompt to be compressed beneath the delimiter (---). To uncompress paste the compressed result prefacted by "uncompress [compressed prompt] or for more detailed recreations "write a detailed uncompressed paragraph based on [compreesed prompt].

[your prompt]
---
AI's Task: Execute the UPC-DP 2.0 Process and Output in Three Sections
I. Analysis Report: Deconstruction of the Input Prompt
(AI: Analyze the "[USER INPUT PROMPT]" above according to the following criteria. Dynamically generate the content for each point based specifically on the provided prompt.)
A. Prompt Content Lexical & Semantic Deconstruction:
1. High-Frequency Terms & Domain-Specific Jargon Identification:
    * (AI: List all terms and phrases from the input prompt that appear repeatedly or are central to its domain. These are prime candidates for abbreviation.)
2. Core Concepts & Abstract Ideas Extraction:
    * (AI: Extract any complex notions, abstract states, foundational principles, or philosophical constructs within the input prompt that could be represented by a single symbol.)
3. Standard Values & Enumerations Cataloging:
    * (AI: Catalog all common boolean states, numerical qualitative states (e.g., "high", "low"), operational modes, or fixed choices present in the input prompt.)
    * (AI: Also, identify explicit mentions or strong implications of "null", "none", "N/A", or "undefined" values that are semantically distinct from an empty string. These will require a specific compact representation.)
4. Compound Data Types & Units Detection:
    * (AI: Identify all instances where numerical values are coupled with units, modifiers, or implied ranges/percentages in the input prompt (e.g., "3000 milliseconds", "512 megabytes", "184 or more", "75 percent").)
5. Implicit Relationships & Operator Identification:
    * (AI: Detect terms or phrasing in the input prompt that imply operations or relationships beyond simple key-value assignment (e.g., "composed of", "transforms to", "greater than", "first...then...", "depends on", "owned by"). These may require custom structural encoding or specific relational tokens.)
6. Structural Components & Hierarchies Mapping:
    * (AI: Map out the discernible structural elements within the input prompt, such as major sections, nested blocks, lists of items, key-value structures, file paths, or communication channels. Identify implicit sequential steps, ownership, or complex dependencies.)
7. Control Flow & Logical Directives Uncovering:
    * (AI: Uncover any explicit or implied conditional statements ("if X then Y"), iterative constructs ("loop always", "retry N times"), sequential instructions, or macro-like patterns in the input prompt.)
8. Meta-Instructions & Interpreter Directives Isolation:
    * (AI: Isolate any parts of the input prompt that appear to be direct commands or formatting instructions specifically targeting the AI/parser itself, rather than configuring a system (e.g., "return all outputs", "do not rephrase", "boot++"). These will be analyzed for potential structured representations.)
9. Identified Ambiguities & Resolution Strategy for this Prompt:
    * (AI: Crucially, identify any specific terms, phrases, or structural interpretations within this particular input prompt that could be genuinely ambiguous to a machine. For each ambiguity, state how the custom protocol (to be designed in Section II) will explicitly resolve it. Also, explicitly identify if any identified ambiguity is deemed unresolvable within the constraints of deterministic parsing and the protocol's design goals, and how that will be handled (e.g., by explicit error or by a defined "best effort" interpretation, if allowed).)
    * Resolution Strategy Outline (AI will specify the actual resolution in Section II): Ambiguities will be resolved via:
        * Contextual Lexicon Sets (CLX): Dynamic abbreviation mapping based on parent key.
        * Explicit Type Annotations (ETA): For ambiguous values.
        * Binding Operator Precedence: Differentiating = and : by context and priority.
        * Schema-Driven Interpretation: Parser's predefined rules.
        * Explicit Grouping/Parenthesization: If required for structural clarity.
B. Platform & Context Assumptions (for this execution):
* Target Parser Capabilities: Assumed to be a highly intelligent, semantic-aware system capable of full UTF-8 processing, robust Abstract Syntax Tree (AST) building, schema-driven lookup, and dynamic execution of control flow and macro expansions. It can discern and act upon meta-directives. The parser is capable of generating a formal EBNF from the protocol specification.
* Character Set: Full UTF-8 support is assumed for all symbolic and character encodement.
* Default Design Goals for this Protocol (AI will adhere to these choices for the custom protocol):
    * Lossless Fidelity: Mandatory and absolute.
    * Maximal Compression: High priority.
    * Moderate Obfuscation: Semantic-based (via custom symbols, abbreviations, custom syntax); cryptographic (encryption, hashing) capabilities are integrated as explicit options where relevant sensitive content is identified or implied.
    * Parser Comprehensibility: Mandatory and unambiguous.
    * Extensibility: High priority via versioning, flexible definition scopes, and external manifests.
    * Security: Basic integrity (EIC) and explicit encryption hooks (MEB) are integrated as standard options.
    * Latency: Optimized for deterministic parsing and semantic fidelity, not raw character-by-character speed (semantic lookups introduce inherent overhead).
C. Scope & Input Type Clarification & Pre-Compression Handling:
1. Input Scope & Fallback for Unstructured Content: This protocol is specifically optimized for input prompts containing structured, semi-structured, or repetitive natural language elements suitable for semantic abstraction.
    * If the analysis in I.A reveals no discernible semantic elements, structure, or repetitive patterns (i.e., a purely free-form narrative prompt), the custom protocol generated in Section II will fall back to a minimal compression strategy:
        * Whitespace stripping (Phase 2.B.7).
        * Basic literal quoting (Phase 2.B.8).
        * A generalized Run-Length Encoding (RLE) will be dynamically applied if significant character repetition (more than 3 consecutive identical characters) is detected and provides an actual compression benefit (reducing the output length).
        * No semantic abbreviations, symbols, or complex structural rules will be generated.
    * The protocol will explicitly state this fallback in Section II if it applies.
2. Comment Handling (Pre-Compression): Any line in the verbose input starting with # or // (after trimming leading whitespace) is considered a comment and is entirely discarded. Any text following # or // on the same line as a semantic KEY=VALUE pair or similar structure will be parsed as part of the VALUE itself, unless explicitly quoted. To denote a comment that should be stripped, it must appear on its own separate line.
D. AI's Internal Design Decision Hierarchy (for Trade-offs & Ambiguity Resolution):
When generating the custom protocol in Section II, the AI will prioritize design choices based on the following hierarchy (highest to lowest):
1. Absolute Lossless Fidelity: Always paramount. If a design choice introduces potential data loss or semantic ambiguity in reconstruction, it is rejected.
2. Unambiguous Parser Comprehensibility: If a choice leads to non-deterministic parsing or ambiguous grammar, it is rejected.
3. Security/Integrity (if identified/implied): If the prompt implies sensitive data or requires high integrity, relevant security mechanisms (MEB, EIC) are prioritized.
4. Maximal Compression: Between two equally lossless, unambiguous, and secure options, the one yielding higher compression is chosen.
5. Extensibility & Modularity: Solutions that allow for easier future expansion or modification are preferred over rigid ones.
6. Human Readability (for Authorized Users): Among options that satisfy higher priorities, the one that is marginally more understandable to a human with the protocol documentation is preferred.

II. Custom Compression Protocol Definition: [Dynamically Generated Protocol Name - e.g., 'PROMPT_ABC-CMP-2.0']
(AI: Based on the exhaustive analysis in Section I and adhering to the Design Decision Hierarchy in I.D, dynamically generate a full, "no stone unturned" custom compression protocol specification for the "[USER INPUT PROMPT]". This section is the generated protocol, including its formal EBNF grammar.)
Protocol Name: [AI: Generate a unique, concise name for this custom protocol. This name will be derived deterministically by taking the SHA256 hash of the alphabetically sorted list of the top-5 identified high-frequency terms (from I.A.1, or top-5 distinct terms from the entire prompt if less than 5 high-frequency terms), truncated to 12 alphanumeric characters, with a version suffix (e.g., SHA_TOP5_XYZ123-2.0). If the prompt is purely unstructured (I.C.1 fallback), the name will be UNSTRUC_COMP_V2.0.]
A. Formal Grammar (EBNF Specification): (AI: Generate a complete and formal EBNF (Extended Backus-Naur Form) grammar for this custom protocol. This grammar will precisely define all syntactic elements, their relationships, and parsing precedence. This is a critical output artifact that defines the language's structure. If the fallback to unstructured content applies (I.C.1), provide a minimal EBNF for quoted literals and RLE.)
code
Ebnf

IGNORE_WHEN_COPYING_START
IGNORE_WHEN_COPYING_END
    
(* AI: Generate the EBNF here based on the protocol rules and your specific input prompt's elements. *)
(* Include definitions for all custom abbreviations, symbols, delimiters, operators, and structural components. *)
(* Ensure the EBNF is context-free and unambiguous. *)
(* Example structure: *)
(* protocol         ::= (root_block | fallback_compressed_string) EOL *)
(* root_block       ::= "::" root_name "::" (global_def | global_param | block)* *)
(* KEY_ID           ::= <alphanumeric_abbreviation> | <symbolic_encapsulation_token> *)
(* VALUE            ::= LITERAL_STRING | NUMBER | BOOLEAN | COMPOUND_VALUE | LIST_VALUE | REF_TOKEN | SYMBOLIC_TOKEN | NULL_TOKEN *)
(* NULL_TOKEN       ::= "_NUL_" (* or other generated token for null semantics *) *)
(* ... and so on, for all rules below. *)
  
B. Phase 1: Lexical & Semantic Foundation (Maximized Compression & Fidelity)
1. Global Abbreviations & Domain-Specific Lexicon:
    * Mechanism: Maps high-frequency and domain-specific terms (from I.A.1) to custom, concise abbreviations.
    * Deterministic Abbreviation Generation Strategy: Abbreviations are generated using a consistent, deterministic algorithm (e.g., if term length > 4, remove vowels, then take first letter + unique hash suffix; else, use first 3 letters + unique hash suffix; ensure generated abbreviations do not conflict with protocol keywords/delimiters).
    * Custom Dictionary for this Prompt:
        * (AI: List all generated Verbose Term → Abbreviated Term mappings based on I.A.1 and the deterministic generation strategy. Ensure uniqueness for each abbreviation or note if CLX is used to resolve collisions.)
    * Lossless & Parser Comprehensible: Parser's schema incorporates this exact dictionary for deterministic lookup.
2. Shorthand Values & Fixed Enumerations:
    * Mechanism: Maps standard values and enumerated choices (from I.A.3) to their shortest forms. This includes a specific, explicitly defined token for "null" or "undefined" semantics.
    * Custom Mappings for this Prompt:
        * (AI: List all generated Verbose Value → Shorthand Value mappings based on I.A.3. Include the specific token for null/none/N/A if identified, e.g., _NUL_ or ∅.)
    * Lossless & Parser Comprehensible: Parser's schema explicitly defines these mappings.
3. Symbolic Encapsulation (SEM) with Explicit Map Referencing:
    * Mechanism: Maps core concepts (from I.A.2) to unique Unicode symbols. A SYM_MAP_ID is included in the root block. This SYM_MAP_ID is strictly global-scoped and cannot be locally overridden.
    * Custom Symbols for this Prompt:
        * (AI: List all generated Concept → Symbol mappings based on I.A.2. Ensure symbols are distinct and fit the UTF-8 character set. Prioritize widely recognized symbols if they semantically fit, otherwise generate suitable, distinct Unicode symbols. If a symbol is generated, its full semantic meaning must be recoverable.)
    * SYM_MAP_ID: [AI: Generate a unique, deterministic ID for this symbol set, e.g., PROTOCOL_NAME_SYM_V1, by taking the SHA256 hash of the alphabetically sorted list of the generated symbol mappings, truncated to 8 alphanumeric characters.]
    * Lossless & Parser Comprehensible: Parser uses SYM_MAP_ID to load the exact symbol dictionary for deterministic translation.
4. Contextual Lexicon Sets (CLX) with Schema-Driven Activation:
    * Mechanism: If ambiguities (from I.A.9) require it, specific ParentKeys map to dedicated LexiconSetIDs containing context-specific abbreviations.
    * Custom CLX Definitions for this Prompt:
        * (AI: Define specific CLX rules only if ambiguities detected in I.A.9 require them. Provide explicit examples of ParentKey → LexiconSetID and the sub-dictionaries used to resolve the identified ambiguities. If no CLX rules are needed, state "No CLX rules required for this prompt's ambiguities.")
    * Lossless & Parser Comprehensible: Parser's schema integrates these specific contextual mappings.
5. Compound Data Types & Units as Atomic Values:
    * Mechanism: Patterns detected in your prompt (from I.A.4) are defined as fused tokens with specific parsing rules.
    * Custom Patterns for this Prompt:
        * (AI: List all generated Pattern (e.g., INTEGER+ms) → Semantic Object (e.g., DURATION) definitions based on I.A.4, specifying the internal structure of the semantic object (e.g., {value: 3000, unit: "ms"}).)
    * Lossless & Parser Comprehensible: Parser's schema defines explicit regex/parsing rules for each pattern.
6. Operator Overloading & Contextual Semantics of Operators:
    * Mechanism: Implicit operators (from I.A.5) are formally defined with context-dependent meanings.
    * Custom Operator Rules for this Prompt:
        * (AI: List all generated Operator → Contextual Meaning (e.g., IF (operand_type=numeric, next_char='+') THEN MIN_THRESHOLD) rules based on I.A.5. Ensure each rule is unambiguous across all contexts. If no custom operators are derived, state "No custom operator overloading derived.")
    * Lossless & Parser Comprehensible: Parser's semantic rules deterministically interpret operators based on context and type.
C. Phase 2: Structural & Syntactic Condensation (Maximized Format Efficiency)
1. Character Set & Overall Encodement:
    * Mechanism: Hybrid ASCII alphanumeric + UTF-8 Unicode symbols. The final compressed string is strictly UTF-8 encoded.
    * Lossless & Parser Comprehensible: Parser fully supports UTF-8; each character is a distinct token as defined by the EBNF.
2. Core Delimiters & Binding Operators:
    * Mechanism: The following delimiters are used: :: (major block), | (top-level KVP/block separator), [ / ] (ordered lists/sub-configs), { / } (unordered sets/parameters in paths), , (list item separator), ; (KVP separator within blocks).
    * Binding Operators:
        * = (KEY=VALUE): The primary, general-purpose assignment operator for standard configuration parameters.
        * : (KEY:VALUE): A secondary binding operator used specifically for flag assignments or attribute setters within special meta-contexts (e.g., ::AUTORUN:: directives, or as a value modifier like VALUE:TYPE_ID).
    * Precedence: = is general assignment. : used within meta-directive blocks (like ::AUTORUN::) has higher precedence for relevant keys and acts as a direct interpreter instruction override. When used as a value modifier (e.g., VAR=val:type), it modifies the preceding value. Strict rules defined in EBNF.
    * Lossless & Parser Comprehensible: The defined EBNF grammar (Section II.A) precisely specifies all delimiters and the strict precedence rules for = vs. : in all contexts, ensuring unambiguous parsing.
3. List & Collection Encoding with Reconstruction Directives:
    * Mechanism: Related items are grouped in [] (ordered lists or arrays) or {} (unordered sets or specific parameter groups). Specific directives (RNG:, ENC=CSV,D=) can further compress homogeneous, repetitive, or serialized data.
    * Heterogeneous List Content: Lists explicitly allow a mix of different element types: scalar values (strings, numbers, symbols), embedded key-value pairs, or identifiers. Each item is strictly delimited by ,.
    * List-Item Attributes/Modifiers: If identified in I.A.9, syntax like =KEY:VALUE is parsed as an attribute or modifier that applies to the preceding semantic block or sequence of items within the list, as defined by the parser's schema for that specific key, not a standalone item.
    * Empty Values & Trailing Delimiters:
        * An explicit KEY= (a key without an assigned value) is deterministically parsed as assigning an empty string ("") to that key.
        * An empty list item (e.g., [A,,B]) is parsed as [A, "", B], inserting an empty string.
        * A trailing comma at the end of a list (e.g., [A,B,]) is explicitly ignored by the parser and does not generate an empty item.
    * Lossless & Parser Comprehensible: The parser's EBNF grammar rigorously defines all list-handling rules, including mixed content, list-item attributes/modifiers, and rules for empty values/trailing delimiters. All ambiguity is eliminated, guaranteeing perfect reconstruction.
4. Wildcard & Pattern Matching Syntax:
    * Mechanism: * represents "any" or "all" in file paths, directory structures, or specific value patterns. {...} enumerates a specific list of items or channels within a path component (e.g., IPC=/chan{sys,chem,...}).
    * Lossless & Parser Comprehensible: The parser's relevant modules have predefined semantics for * and {} as pattern-matching directives, ensuring they are interpreted as rules, not literal path components.
5. Named Reference Tokens (NRT) Definition:
    * Mechanism: ::DEF::[ID=VALUE] for declaration and ^ID for reference.
    * Scope Rules: Local definitions (nested ::DEF:: blocks) override global definitions. The innermost scope takes precedence.
    * Lossless & Parser Comprehensible: Parser manages a scope stack for deterministic lookup and substitution.
6. Schema-Driven Omission (SDO) of Default Values:
    * Mechanism: If a parameter's value in the verbose input is identical to its predefined default value (as per the parser's internal schema for that key and context), that parameter is omitted from the compressed string.
    * Lossless & Parser Comprehensible: The parser, with its complete schema knowledge, always inserts the correct default for omitted parameters during reconstruction.
7. Whitespace Removal:
    * Mechanism: All extraneous whitespace (multiple consecutive spaces, newlines, and single spaces not within literal string values) is removed during compression.
    * Lossless & Parser Comprehensible: Whitespace is non-semantic (except within quoted literals); its removal is lossless.
8. Explicit Quoting Rules:
    * Mechanism: Literal strings containing delimiters (=, :, |, [, ], {, }, ,, ;, *, ^, (space)) or special characters that would conflict with the protocol's syntax must be enclosed in single quotes (') or double quotes ("). Nested quotes are explicitly escaped (e.g., \', \"). This mechanism also applies to any literal text in the user's prompt that happens to match the meta-protocol's own syntax (::DEF::, ^ID, etc.) but is intended as literal content for the custom protocol.
    * Lossless & Parser Comprehensible: Parser applies strict quoting rules for identifying and preserving literal string content.
9. Order of Operations for Nested Structural Elements:
    * Mechanism: Parsing of structural elements adheres to standard nested grammar rules: innermost blocks are parsed first. Within a block, KEY=VALUE and KEY:VALUE pairs are processed left-to-right. For lists, items are processed left-to-right, with list-item attributes applying to their defined scope.
    * Lossless & Parser Comprehensible: Parser follows a deterministic, unambiguous parsing order based on the defined EBNF grammar.
10. Handling of Empty Blocks or Sections:
    * Mechanism: An explicitly declared empty block (e.g., BLOCK[] or ::EMPTY_SECTION::) is retained in the compressed output if its omission would be semantically ambiguous with a schema default (e.g., "no mods" is a specific state vs. "mods not specified, use default"). Otherwise, empty blocks may be omitted under SDO.
    * Lossless & Parser Comprehensible: Parser explicitly checks schema context for empty block semantics during both compression and decompression.
11. Generalized Run-Length Encoding (RLE) (Fallback for Unstructured):
    * Mechanism: If the protocol falls back to minimal compression (I.C.1), RLE will be applied to sequences of 4 or more identical characters. The format will be (char)N where char is the repeated character and N is the count. E.g., AAAA becomes (A)4.
    * Lossless & Parser Comprehensible: RLE transformation is fully reversible.
D. Phase 3: Advanced Logic & Control Flow (Dynamic Configuration Generation)
1. Deterministic Control Flow Language (DCFL):
    * Mechanism: Keywords IF, THEN, ELSE, FOR, IN, DO and their precise grammar are defined if identified in I.A.7.
    * Custom DCFL for this Prompt: (AI: List specific rules only if control flow constructs are identified in I.A.7, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser builds an AST for logic, enabling perfect reconstruction.
2. Scheduled & Event-Driven Triggers (SET):
    * Mechanism: Structured syntax for CRON, FS events, etc. if identified in I.A.7.
    * Custom SET for this Prompt: (AI: List specific rules only if triggers are identified in I.A.7, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser reconstructs explicit trigger definitions.
3. Macro/Function Definitions with Parameters (MFD):
    * Mechanism: MACRO[ID(P):[BLOCK]] and CALL[ID(V)] if complex reusable patterns found in I.A.7.
    * Custom MFD for this Prompt: (AI: List specific rules only if reusable patterns are identified in I.A.7, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser performs semantic substitution, perfect reconstruction.
4. Explicit Type Annotations (ETA):
    * Mechanism: VALUE:TYPE_ID for type hints (e.g., int, str, bool, dur, flt). Used for ambiguous values identified in I.A.9 or when precision is required.
    * Custom ETA for this Prompt: (AI: List specific rules only if type ambiguities or precision needs are identified in I.A.9, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser strictly adheres to annotations for casting and validation.
E. Phase 4: Obfuscation & Security Mechanisms (Intentional Concealment & Integrity)
1. Embedded Integrity Checksums (EIC) per Block:
    * Mechanism: KEY=VALUE;CHK=HASH_VAL. Uses a truncated SHA256 hash.
    * Lossless & Parser Comprehensible: Checksum is metadata; content is fully parsable and verifiable.
2. Mandatory Encryption Blocks (MEB) with Header:
    * Mechanism: ::ENC_BLOCK::ALG=AES256,KEY_ID=...,DATA=BASE64_CIPHERTEXT::.
    * Lossless & Parser Comprehensible: Protocol defines encrypted state; decryption recovers original plaintext.
3. Semantic Noise & Decoy Elements (SND) with IGNORE Directive:
    * Mechanism: KEY=VALUE,IGNORE=ON.
    * Lossless & Parser Comprehensible: Parser parses but excludes from functional config, preserving the decoy data.
4. Explicit Padding Directive (PAD):
    * Mechanism: PAD=ON[maxlen=N,fill=CHAR]. Pads entire string or block.
    * Lossless & Parser Comprehensible: Parser removes/reapplies padding; core data untouched.
F. Phase 5: Meta-Configuration & Interpreter Directives (Protocol Management)
1. Protocol Version & Feature Flags:
    * Mechanism: ACP_VER=2.0. FEAT_FLAGS lists all features used in this specific generated protocol.
    * Lossless & Parser Comprehensible: Parser dynamically adjusts rules based on version/flags.
2. Runtime Context Requirements (RCR):
    * Mechanism: REQ[OS=...,MEM=...,LIB_VER=...] if relevant requirements found in I.A.7.
    * Custom RCR for this Prompt: (AI: List specific rules only if runtime requirements are identified in I.A.7, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser validates environment.
3. External Resource Manifest (ERM):
    * Mechanism: ::EXT_RES::[SCHEMA_URI=...,SYM_MAP_URI=...] if external resources are needed for this prompt's protocol.
    * Custom ERM for this Prompt: (AI: List specific rules only if external resources are identified as necessary, using the EBNF.)
    * Lossless & Parser Comprehensible: Parser fetches external data for reconstruction.
4. Meta-Directives (MDI) for Interpreter:
    * Mechanism: Instructions directly targeting the interpreter (from I.A.8).
    * Root Configuration Block Type: ::[AI: Determine the most appropriate root block name from I.A.6 or I.A.8 based on the prompt's content (e.g., 'BOOTABLE_SEED', 'CONFIG_ROOT'). If no clear root, use ::GENERIC_CONF::. This defines the primary context and initial parser modes for the entire configuration.]::
    * Custom MDI for this Prompt:
        * (AI: For MDI identified in I.A.8, first attempt to generate structured representations if patterns emerge (e.g., RETURN ALL OUTPUTS >300 IN PARTS could become RET[ALL=ON,LIMIT=300,MODE=PARTIAL]). Only if no clear structured pattern is discernible, then list the MDI as literal strings for direct interpreter action. Specify these rules using the EBNF.)
    * Lossless & Parser Comprehensible: Parser/meta-interpreter has predefined handlers for these commands; structured MDI are parsed semantically, while literal MDI are treated as exact literal instructions.
5. Conflict Resolution Logic:
    * Mechanism: Strict precedence hierarchy:
        * MDI directives (highest).
        * Local ::DEF:: overrides.
        * Global ::DEF:::: definitions.
        * Explicit Global Parameters.
        * Schema Defaults (SDO) (lowest).
    * Lossless & Parser Comprehensible: Parser applies these rules deterministically.

III. Compressed Output of Your Prompt:
(AI: Apply the custom compression protocol designed in Section II to the original "[USER INPUT PROMPT]". Generate the final, compressed string here.)
::[AI: Dynamically generated Root Block Name from II.E.4]::[AI: Compressed content of the user's prompt according to the custom protocol]::EOL::
