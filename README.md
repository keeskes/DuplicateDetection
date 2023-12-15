# DuplicateDetection

This Python script aims to identify duplicate products within a dataset of TVs (TVs-all-merged.json). It implements a pipeline for cleaning titles, generating binary and signature matrices, applying LSH, and performing a Multi-component Similarity Measure (MSM) to identify potential duplicate pairs based on their titles and additional product information. This code explores various combinations of hyperparameters (bandwidth, similarity thresholds, weights) for identifying duplicates efficiently.

Structure:

Data Loading and Cleaning: Loads JSON data, cleans titles, and extracts relevant information (brand names, colors).

Methods belonging to this group:
cleaning_steps
extract_title_words
append_product_color
append_brand_info
clean_titles

Binary & Signature Matrices: Creates a binary matrix representing product descriptions and generates MinHash signatures for efficient similarity comparisons.

Methods belonging to this group:
create_binary_matrix
generate_hashvalues
generate_signatures

Locality-Sensitive Hashing (LSH): Hashes signatures into buckets to identify candidate pairs efficiently.

Methods belonging to this group:
hash_signatures_to_buckets
signature_to_bands
find_candidate_pairs

Multi-component Similarity Measure (MSM): Applies a weighted measure (Q-grams & Jaccard) to refine and identify potential duplicates from candidate pairs.

Method belonging to this group: 
MSM

Evaluation Metrics: Evaluates the model using Precision, Recall, F1-score, and more based on True Positives and comparison fractions.

Methods belonging to this group:
sample_data
true_positives
total_num_duplicates
sort_sets
computeMeasures
compute_metrics

Usage:

Ensure 'TVs-all-merged.json' file is in the same directory.
Adjust hyperparameters (e.g., bandwidths, similarity thresholds, weights) for optimal duplicate detection.
Run the code and visualize the evaluation metrics to understand the effectiveness of duplicate detection under different parameter settings.
