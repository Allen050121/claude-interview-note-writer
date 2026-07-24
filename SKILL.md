---
name: interview-note-writer
description: Write or reorganize Chinese interview 八股文 notes in this vault's 基础面试题 structure. Use when creating, expanding, or standardizing Java/Python/backend/AI interview knowledge notes with module indexes under 基础面试题/0.目录 and per-topic Markdown files under 基础面试题 module folders such as 1.Java基础.
---

# Interview Note Writer

Use this skill to create or update interview-prep notes that match this vault's existing `基础面试题` style.

## Source Structure

Use this layout:

```text
基础面试题/
  0.目录/
    1.Java基础.md
    2.Java集合.md
    ...
  1.Java基础/
    基本数据类型.md
    String StringBuffer StringBuilder.md
    ...
```

Before writing, inspect the target module index in `基础面试题/0.目录/` and at least 3 strong nearby topic files in the matching module folder. For Java-style tone and density, prefer comparing against files such as `基本数据类型.md`, `String StringBuffer StringBuilder.md`, and `异常处理.md` when they are relevant. Preserve the local naming, ordering, link style, and answer tone.

## Module Index Format

Write module index files as grouped third-level headings:

```markdown
### Java 基本语法与数据类型

- 理解基本数据类型与引用数据类型的区别
  - [基本数据类型](../1.Java基础/基本数据类型.md)
  - [引用数据类型](../1.Java基础/引用数据类型.md)
- 掌握包装类的使用
  - [包装类](../1.Java基础/包装类.md)
```

Rules:

- Use `###` for large submodules inside one subject.
- Use a top-level bullet for the learning objective, usually starting with `理解`、`掌握`、`熟悉`、`了解`.
- Put one or more nested Markdown links under each objective.
- Link relatively from `0.目录/<模块>.md` to `../<序号.模块名>/<知识点文件>.md`.
- Encode spaces in links as `%20`; keep Chinese characters readable unless existing files in that index use another style.
- If several objectives point to one file, reuse the same link instead of creating duplicate files.

## Topic File Format

Each knowledge-point file is a sequence of interview questions and answers. The structure is mandatory because the notes are meant to be read like a book: the user should be able to scan `###` headings, jump to the exact question, and see the wanted answer immediately below it. Do not add frontmatter, H1, H2, table of contents, or summary sections unless the surrounding files already use them.

Use this shape:

```markdown
### 核心问题放在第一位？

先直接回答结论，再解释原因、机制和面试中应该怎么说。文字讲清楚即可，不要为了显得完整而堆代码。

### 常见追问是什么？

继续用面试回答的口吻展开。必要时给出边界条件、使用场景、坑点或项目实践。
```

Rules:

- Use only `### 问题？` as the primary structure.
- Put the most central,最高频,最能概括该知识点的问题 first. The first answer should be useful within the first screen after opening the file.
- Follow with extension questions from basic to deeper:
  - 定义/区别
  - 底层原理
  - 使用场景
  - 常见坑
  - 性能/并发/内存影响
  - JDK 版本差异
  - 项目实践
  - 面试官可能继续追问的问题
- Prefer 8-15 questions for a normal topic. Use fewer for tiny topics and more for broad topics.
- Every normal answer should have enough substance for an interview, but do not force the same template onto every question. Choose the natural shape of the answer based on the question type.
- Do not write thin one-sentence answers unless the question is genuinely trivial.
- Keep each answer mostly prose. Use code only when prose cannot make the point clear.
- When adding code, use short fenced Java snippets and immediately explain what the code demonstrates.
- Avoid turning a note into a code tutorial. In most files, code should be occasional support, not the main body.

## Answer Style

Write in concise Chinese interview style:

- Start with the answer, then explain. The first sentence should make the conclusion clear.
- Prefer paragraphs over long lists unless comparing choices or enumerating steps.
- Highlight key terms with `**加粗**` sparingly.
- Use practical wording: "实际项目中..."、"面试时可以这样说..."、"需要注意的是...".
- Add "为什么", "什么时候用", "容易踩什么坑", or "和谁对比" only when the current question needs it. Do not mechanically include all of them in every answer.
- Avoid textbook padding, empty definitions, pure copy-paste API lists, and generic AI filler.
- Do not pad with low-value code examples. If an interviewer would not care about the code during an oral interview, explain the point in prose instead.
- Do not be lazy: if a question is important, include the details that make that specific answer useful, such as the key mechanism, contrast, boundary condition, or practical caveat.
- Avoid unsupported precision. For version-specific details, mention the version clearly, such as `JDK 8` or `JDK 9+`.

## Answer Shape

Choose the answer shape from the question, following the existing Java notes:

- Definition questions can be short and direct, like "多态是指..." plus one sentence that makes it memorable.
- Condition questions can use compact numbered points, like "多态的三个必要条件".
- Difference/comparison questions should compare by clear dimensions, such as 方法实现、成员变量、继承限制、线程安全、性能、使用场景.
- Principle questions should explain the core mechanism, but only go as deep as interview recall needs.
- Selection/scenario questions should say when to choose each option and give one practical example if useful.
- Pitfall questions should explain the wrong practice and the reason it causes problems.
- Very small factual questions can be brief. Do not inflate them just to meet a length target.

## Quality Checklist

Before finishing:

- The module index links resolve to files that exist.
- New topic filenames exactly match their index link text and path.
- The first `###` question is the core interview question.
- Every topic includes meaningful extension questions, not only one main answer.
- Answers are not too thin, but they also do not mechanically follow a fixed "结论 + 原因 + 场景 + 坑点 + 对比" formula.
- Code snippets are short, correct, and used only to clarify.
- Code does not dominate the note.
- Markdown remains UTF-8 and consistent with neighboring notes.
