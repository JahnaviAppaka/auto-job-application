
## Development

### Scripts

*(Add any build scripts or helper scripts here if you have them, e.g., for linting, bundling with Webpack/Parcel, etc. For now, it's likely manual loading.)*

*   **Reloading:** After making changes to the code, you need to reload the extension from your browser's extension management page.

### Key Files

*   `manifest.json`: Defines the extension's capabilities, permissions, and entry points.
*   `options/options.js`: Handles the logic for saving and loading the user's profile.
*   `content_scripts/content.js`: The core logic for interacting with web pages, identifying form fields, displaying the mapping UI, and filling forms.
*   `popup/popup.js`: Manages the user interface of the browser action popup and dispatches actions to the content script.
*   `background.js`: Handles background events. In later phases, it might manage communication with a backend for LLM API calls.

## Contributing

This project is currently an MVP. Contributions, bug reports, and feature suggestions are welcome! Please feel free to:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -am 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

Please ensure your code follows existing styling and includes relevant tests if applicable.

## Future Work / Roadmap

*   **Phase 2 (LLM Field Recognition):**
    *   [ ] Securely integrate with an LLM API via a backend service.
    *   [ ] Send form field context (labels, placeholders, surrounding HTML) to LLM.
    *   [ ] LLM suggests the type of information each field requires (e.g., "First Name," "Email," "Years of Experience").
    *   [ ] Automatically pre-select mappings based on LLM suggestions, allowing user correction.
*   **Phase 3 (LLM Answer Generation):**
    *   [ ] Send qualitative questions, user profile, and job description to LLM.
    *   [ ] LLM generates draft answers for questions like "Why are you interested in this role?".
    *   [ ] User reviews and edits AI-generated answers before they are filled.
*   **Advanced Mapping UI:**
    *   [ ] Better handling for mapping array items (e.g., "Work Experience #1 - Company", "Work Experience #2 - Company").
    *   [ ] More robust field identification using selectors or visual cues if possible (beyond MVP).
*   **File Upload Assistance:**
    *   [ ] More clearly guide users to the correct file input for resumes/cover letters.
    *   [ ] (Advanced) Explore secure ways to pre-fill file inputs if browser APIs allow.
*   **Error Handling & UX Improvements:**
    *   [ ] More graceful error handling and user feedback.
    *   [ ] Onboarding tutorial for new users.
*   **Job Description Parsing:**
    *   [ ] Automatically extract job description text to provide better context to LLMs.
*   **Cloud Sync (Optional):**
    *   [ ] Allow users to (optionally and securely) sync their profile and mappings across devices.

## License

*(Choose a license for your project. MIT is a common and permissive choice.)*

This project is licensed under the [MIT License](LICENSE.txt).
