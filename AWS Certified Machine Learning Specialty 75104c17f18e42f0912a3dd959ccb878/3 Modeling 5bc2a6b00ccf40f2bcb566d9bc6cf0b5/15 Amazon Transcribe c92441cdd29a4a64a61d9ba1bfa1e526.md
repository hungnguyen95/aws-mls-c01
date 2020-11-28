# 15. Amazon Transcribe

- Speech to text
    - Input in FLAC, MP3, MP4, or WAV, in a specified language
    - Streaming audio supported (HTTP/2 or WebSocket)
        - French, English, Spanish only
- Speaker Identificiation
    - Specify number of speakers
- Channel Identification
    - i.e., two callers could be transcribed separately
    - Merging based on timing of “utterances”
- Custom Vocabularies
    - Vocabulary Lists (just a list of special words – names, acronyms)
    - Vocabulary Tables (can include “SoundsLike”, “IPA”, and “DisplayAs”)