# Vocabulary Files

This folder contains vocabulary flashcard files generated from TryHackMe notes.

## Structure

```
vocabulary/
└── <Subdirectory>/          # Mirrors the note subdirectory name
    └── <note_name>.txt      # One .txt per .md note file
```

The subdirectory names correspond to subdirectories found under `notes/tryhackme/`.
Each `.txt` file corresponds to a `.md` note file within that subdirectory.

**Example:**

- Notes source: `notes/tryhackme/networking fundamentals/1. what_is_networking(addresses).md`
- Vocabulary output: `vocabulary/Network Fundamentals/networking_basics.txt`

## Vocabulary File Format

Each line in a `.txt` file follows this pipe-delimited format:

```
Term|Definition|category
```

**Example:**

```
OSI Model|Open Systems Interconnection Model; a 7-layer framework that standardizes how networked devices send, receive, and interpret data.|OSI model
TCP|Transmission Control Protocol; a Layer 4 protocol that guarantees data delivery through error-checking and maintains a constant connection.|protocol
```

## Generating New Vocabulary Files

To generate new vocabulary files, prompt Claude Code with:

> "Generate new vocabulary files based upon the formatting in the vocabulary folder. The subdirectories within the folder are based upon the folders containing the notes. For example, `/home/malston/tryhackme/notes/tryhackme/networking fundamentals`. The individual .txt's are based upon the .md note files within the `/home/malston/tryhackme/notes/tryhackme` subdirectories."

Claude will:
1. Read all `.md` files in `notes/tryhackme/<subdirectory>/`
2. Extract key terms, definitions, and categories from the content
3. Create a corresponding `.txt` file in `vocabulary/<Subdirectory>/`
4. Format each entry as `Term|Definition|category`
