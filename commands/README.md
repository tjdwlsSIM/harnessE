# Commands

This folder contains slash-style command templates for Codex.

These commands help reuse the harnessE workflow without rewriting long prompts every time.

## Available Commands

```txt
/apply-harness
/feature
/refactor
/review
/fix

/feature 사진 업로드 후 미리보기 기능을 추가해줘

commands/feature.md 기준으로 작업해줘.

요청:
사진 업로드 후 미리보기 기능을 추가해줘.


---

## 4. `commands/README.md`에도 추가

`commands/README.md`의 명령어 목록에 `/gpush` 추가.

```md
## Available Commands

```txt
/apply-harness
/feature
/refactor
/review
/fix
/gpush
```
```

그리고 설명 추가.

```md
### /gpush

Stages, commits, and pushes current changes.

Example:

```txt
/gpush docs: update harnessE command templates
```

This runs:

```bash
git add .
git commit -m "docs: update harnessE command templates"
git push
```
```

---

## 5. Codex에서 실제 사용법

앞으로 Codex에 이렇게 입력하면 돼.

```txt
/gpush docs: add gpush command
```

또는 기능 추가 후:

```txt
/gpush feat: add memory upload preview
```

버그 수정 후:

```txt
/gpush fix: resolve map marker position issue
```

문서 수정 후:

```txt
/gpush docs: update harnessE slash commands
```

---

## 6. 이번 변경사항을 직접 올리는 명령어

지금 `/gpush` 명령어 파일을 만든 뒤에는 직접 터미널에서 이렇게 올리면 돼.

```bash
git add .
git commit -m "docs: add gpush command"
git push
```

정리하면 `commands/gpush.md`를 만들고, `AGENTS.md`에 `/gpush` 매핑만 추가하면 돼.  
앞으로는 Codex에서 `/gpush 커밋메시지` 한 줄로 `add .`, `commit`, `push` 흐름을 시킬 수 있어.