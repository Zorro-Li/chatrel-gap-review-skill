# RAG Analysis Prompt Template

Input:

- normalized_messages: JSON array
- conversation_profile: JSON object
- retrieved_evidence_bundle: JSON object

Task:

Analyze the relationship between the two speakers using the evaluation dimensions.

Required reasoning structure:

1. Read the conversation profile and decide data sufficiency.
2. Segment messages by time window.
3. Compute observable features only from the data.
4. For each dimension, connect features to retrieved evidence.
5. Assign confidence by data sufficiency and evidence quality.
6. Return the final report using `output_schema.json`.

Dimension order:

1. data_sufficiency
2. relationship_context
3. tie_strength
4. reciprocity_balance
5. response_dynamics
6. topic_continuity
7. lexical_alignment
8. emotion_affect
9. social_support
10. rapport_trust_intimacy
11. power_role
12. conflict_repair
13. modality_media
14. temporal_trajectory
15. safety_caveats

Evidence rule:

- Every interpretive paragraph should cite at least one retrieved chunk id.
- If a dimension has weak evidence, say the dimension is low confidence and name the missing data.

