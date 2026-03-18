# notemaster-333540-333555

## Database Schema

### notes
- `id` (SERIAL PRIMARY KEY)
- `title` (TEXT NOT NULL)
- `content` (TEXT)
- `is_archived` (BOOLEAN DEFAULT FALSE)
- `is_pinned` (BOOLEAN DEFAULT FALSE)
- `created_at` (TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP)
- `updated_at` (TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP)

### tags
- `id` (SERIAL PRIMARY KEY)
- `name` (TEXT UNIQUE NOT NULL)

### note_tags
- `note_id` (INTEGER REFERENCES notes(id) ON DELETE CASCADE)
- `tag_id` (INTEGER REFERENCES tags(id) ON DELETE CASCADE)
- PRIMARY KEY (note_id, tag_id)
