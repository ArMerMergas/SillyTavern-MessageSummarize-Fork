# Message Summarize (Fork)

This is a modified version of the **Message Summarize** extension for SillyTavern.
**Original extension by [qvink](https://github.com/qvink/SillyTavern-MessageSummarize).**

Please refer to the original repository for full documentation on basic usage.
- Install the extension in ST using the github link: https://github.com/ArMerMergas/SillyTavern-MessageSummarize-Fork.git

## 🚀 Key Changes & New Features

### 1. Aggressive Summarization Mode
Added a new "Aggressive" mode to save even more context tokens for older messages.
*   **Aggressive Depth Threshold**: Messages older than a configured number (e.g., 20 messages back) will automatically use a different, more concise prompt.
*   **Separate Prompt Editor**: You can fully customize the "Aggressive Prompt", including its own role, prefill, and macros, independent of the standard summary prompt.
*   **Upgrade Button**: A new "Upgrade to Aggressive" button allows you to bulk-resummarize existing memories using the aggressive prompt.

### 2. Performance Optimization (Zero Lag)
*   **O(N) Token Counting**: Completely rewrote the token counting logic used during chat generation.
*   **Eliminated Freezes**: Previously, large chats (1000+ messages) caused 3-4 minute freezes after every summarization due to inefficient O(N²) calculations. Now, it runs instantly with zero lag, regardless of chat size.

### 3. Fallback Mechanism (No Lost Messages)
*   **Full Message Fallback**: If a message is marked for inclusion (e.g., it's old enough) but has no summary generated yet, the extension now automatically inserts the **full message text** into the summary block.
*   **Preserved Chronology**: This ensures that no messages are ever "lost" or skipped, and the chronological order of the conversation is strictly maintained within the memory block.

### 4. UI & Stability Fixes
*   **Memory Edit Interface**: Fixed significant lag when opening the "Edit Memory" window by ensuring filters are reset to a clean state on open.
*   **Filter Fixes**: Added a "No Summary (Bot)" filter to easily find and summarize bot messages.
*   **Bug Fixes**: Resolved various TypeErrors and issues where the aggressive prompt setting was ignored.
