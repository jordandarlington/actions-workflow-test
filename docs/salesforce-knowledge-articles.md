# Salesforce Knowledge Articles: Storage Overview

## Where Are Knowledge Articles Stored?

In Salesforce, Knowledge Articles are stored as records in the **Knowledge object** (API name: `Knowledge__kav`, or `KnowledgeArticleVersion`). Each article version is a separate record within this object.

### Key Storage Details

- **Object**: `KnowledgeArticleVersion` (API name: `Knowledge__kav`)
- **Database**: Salesforce's multi-tenant relational database (Oracle-based infrastructure)
- **Article Content**: Stored in rich text area fields on the Knowledge record
- **Published vs. Draft**: Articles exist in multiple states (`Draft`, `Published`, `Archived`), each represented as a separate version record linked by a master `KnowledgeArticle` record (API name: `KnowledgeArticle`)

### Article Versions and States

| State      | Description                                         |
|------------|-----------------------------------------------------|
| `Draft`    | Work-in-progress article, not visible to end users  |
| `Published`| Live article, visible to users based on data categories and visibility settings |
| `Archived` | Retired article, no longer visible but retained for history |

### Data Categories

Knowledge Articles are organized using **Data Categories**, which control visibility and help users find relevant content. Categories are assigned to articles and map to user profiles or roles via **Data Category Visibility** settings.

### File Attachments

Any files attached to a Knowledge Article are stored in Salesforce's **Content** infrastructure (similar to Salesforce Files / ContentDocument), linked back to the article record.

### Accessing Knowledge Articles

- **Lightning Experience / Salesforce Classic**: Via the *Knowledge* tab or Service Console
- **API**: Via the `KnowledgeArticleVersion` SOQL object or the Knowledge REST API
- **Communities / Experience Cloud**: Surfaced through the embedded Knowledge component

### Further Reading

- [Salesforce Knowledge Documentation](https://help.salesforce.com/s/articleView?id=sf.knowledge_whatis.htm)
- [KnowledgeArticleVersion Object Reference](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_knowledge__kav.htm)
