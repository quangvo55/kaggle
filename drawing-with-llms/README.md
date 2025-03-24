## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Drawing with LLMs Competition

Package Competitions are Code Competitions

Submissions to this competition must be made through Notebooks. In order for the "Submit" button to be active after a commit, the following conditions must be met:

    CPU Notebook <= 9 hours run-time
    GPU Notebook <= 9 hours run-time
    Internet access disabled
    Freely & publicly available external data is allowed, including pre-trained models

Please see the Code Competition FAQ for more information on how to submit. And review the code debugging doc if you are encountering submission errors.

### Evaluation

Submissions are evaluated by the mean CLIP similarity between the given descriptions and the submitted SVG code.

For each given description in the test set, your model must produce an SVG image depicting the scene described. We convert each SVG to a PNG image with the cairosvg Python library and append "SVG illustration of " to each description. We then compute the similarity between the text description and the PNG image as the cosine similarity of their feature embeddings as produced by a SigLIP SoViT-400m model. The final score is the average of these similarity scores.

In order to ensure the generated images adhere to the spirit of the competition, the SVG code must satisfy a number of constraints:

    No SVG may more than 10,000 bytes long.
    Each SVG may only include elements and attributes from an allowlist. Note that CSS style elements are not allowed.
    No SVG may include any rasterized image data or data from external sources.

In addition, the evaluation system requires that:

    Your model returns an SVG within 5 minutes of being passed a description.
    All SVGs are generated in under 9 hours.

Submissions with SVGs violating any of these constraints are invalid.

You may review the implementation of the metric here: SVG Image Fidelity. This metric imports the svg_constraints package defined here: SVG Constraints. You may wish to use this constraints package to help ensure your submissions are valid.

### Timeline

    February 25, 2025 - Start Date.
    May 19, 2025 - Entry Deadline. You must accept the competition rules before this date in order to compete.
    May 19, 2025 - Team Merger Deadline. This is the last day participants may join or merge teams.
    May 27, 2025 - Final Submission Deadline.

All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted. The competition organizers reserve the right to update the contest timeline if they deem it necessary.