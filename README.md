# StudentGrades.md
Database with Entities Student, Enrollment, Class
## Er Diagram on https://mermaid-js.github.io/mermaid-live-editor/#/
```Er
erDiagram
    
    Student ||--o{ Enrollment : has
    Enrollment o{ -- || Class: has
    
    Enrollment{
        int grade
    }

    Student {
        string name
        string email
        string phoneNumber
        boolean isReleased
    }

    Class {
       string name
       string hours 
    }
```
[![](https://mermaid.ink/img/eyJjb2RlIjoiZXJEaWFncmFtXG4gICAgXG4gICAgU3R1ZGVudCB8fC0tb3sgRW5yb2xsbWVudCA6IGhhc1xuICAgIEVucm9sbG1lbnQgb3sgLS0gfHwgQ2xhc3M6IGhhc1xuICAgIFxuICAgIEVucm9sbG1lbnR7XG4gICAgICAgIGludCBncmFkZVxuICAgIH1cblxuICAgIFN0dWRlbnQge1xuICAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgICBzdHJpbmcgZW1haWxcbiAgICAgICAgc3RyaW5nIHBob25lTnVtYmVyXG4gICAgICAgIGJvb2xlYW4gaXNSZWxlYXNlZFxuICAgIH1cblxuICAgIENsYXNzIHtcbiAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgIHN0cmluZyBob3VycyBcbiAgICB9XG5cbiAgIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZXJEaWFncmFtXG4gICAgXG4gICAgU3R1ZGVudCB8fC0tb3sgRW5yb2xsbWVudCA6IGhhc1xuICAgIEVucm9sbG1lbnQgb3sgLS0gfHwgQ2xhc3M6IGhhc1xuICAgIFxuICAgIEVucm9sbG1lbnR7XG4gICAgICAgIGludCBncmFkZVxuICAgIH1cblxuICAgIFN0dWRlbnQge1xuICAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgICBzdHJpbmcgZW1haWxcbiAgICAgICAgc3RyaW5nIHBob25lTnVtYmVyXG4gICAgICAgIGJvb2xlYW4gaXNSZWxlYXNlZFxuICAgIH1cblxuICAgIENsYXNzIHtcbiAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgIHN0cmluZyBob3VycyBcbiAgICB9XG5cbiAgIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)
  
