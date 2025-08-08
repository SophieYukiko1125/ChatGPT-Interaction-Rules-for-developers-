
## 🖼 PowerPoint (.pptx) → Markdown / VBA

### 🔧 Recommended Communication Methods

| Content Type              | Recommended Format         | Description |
|---------------------------|----------------------------|-------------|
| Slide titles & text       | Markdown outline           | Use `#` for titles, `-` for bullet points |
| Repetitive slide structure| VBA                        | Automate slide creation using code |
| Charts or visuals         | Python (e.g. `matplotlib`) or VBA | Reproducible charts in code |
| Layout/theme description  | Structured text or VBA     | Describe layout in code or JSON |
| Animations/transitions    | VBA (if essential)         | Basic support via code |
| Embedded media            | Manual note                | Cannot be efficiently coded; describe content |

### 📑 Example 1: Slide → Markdown

**Original Slide:**

_Title:_ "Q2 Performance"  
_Bullets:_  
- Revenue grew by 18%  
- User base expanded in Asia  
- Challenges in supply chain

**Markdown Equivalent:**

```markdown
## Slide 1: Q2 Performance

- Revenue grew by 18%
- User base expanded in Asia
- Challenges in supply chain
```

### ⚙️ Example 2: Slide → VBA

```vba
Sub CreateSlideDeck()
    Dim pptApp As Object, pptPres As Object
    Set pptApp = CreateObject("PowerPoint.Application")
    pptApp.Visible = True
    Set pptPres = pptApp.Presentations.Add

    ' Slide 1
    With pptPres.Slides.Add(1, 1)
        .Shapes.Title.TextFrame.TextRange.Text = "Q2 Performance"
        .Shapes.Placeholders(2).TextFrame.TextRange.Text = _
            "• Revenue grew by 18%" & vbCrLf & _
            "• User base expanded in Asia" & vbCrLf & _
            "• Challenges in supply chain"
    End With
End Sub
```

### 🧠 Why Use Markdown or VBA?

| Method    | Advantages | When to Use |
|-----------|------------|-------------|
| **Markdown** | Lightweight, readable, good for outlining | Best for summaries or slide drafts |
| **VBA**       | Reproducible, editable, programmable | Best for templated or automated slide generation |

### 🛠️ Tool Suggestions

- Convert `.pptx` to Markdown manually, or by script
- Use VBA to:
  - Create repetitive decks from data (e.g. financial reports)
  - Maintain layout consistency
  - Batch update presentations
