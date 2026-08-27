# fairy_tale_office

`fairy_tale` 크루(창작동화 제작 에이전트들)가 일하는 모습을 보여주는 오피스 화면입니다.

**공방**: https://heekeunlee.github.io/fairy_tale_office/

## 콘셉트

[ai_crew](https://github.com/heekeunlee/ai_crew)의 "오피스" 아이디어에서 출발했지만,
2D 픽셀 캐릭터 대신 **촛불 켜진 목재 공방의 벽장(니치) 캐비닛**으로 다시 그렸습니다.
각 에이전트는 자리가 아니라 자신을 상징하는 도구(컴퍼스, 깃펜, 봉랍 등)로 표현됩니다.

- **지금 문을 연 방** — 실제로 존재하는 에이전트 3명(기획자·작가·심사위원). 촛불이 켜져 있습니다.
- **다음에 합류할 이웃들** — 아직 만들지 않은 역할(트렌드 리서처·북디자이너·마케터·총무). 흐릿하게 "준비 중"으로 표시됩니다.
- **일하는 순서** — `/plan → /write → /review` 흐름.

## 지금은 반자동입니다

`fairy_tale` 본체는 아직 GitHub Actions로 자동 근무하지 않습니다. 사람이 맥미니에서
Claude Code 슬래시 커맨드(`/plan`, `/write`, `/review`)를 직접 실행해야 이야기가 진행됩니다.
그래서 이 화면은 실시간 근무 상태를 보여주는 대시보드가 아니라, **크루 구성과 진행 방식을
보여주는 정적인 안내판**입니다. 없는 사실(실시간 자동 근무)을 지어내지 않습니다.

## 구조

```
site/
  index.html    오피스 화면 (정적 HTML, 외부 JS 의존성 없음)
  .nojekyll     GitHub Pages가 Jekyll로 처리하지 않도록
.github/workflows/
  pages.yml     site/ 를 GitHub Pages로 배포
```

## 로컬에서 보기

```bash
cd site && python3 -m http.server 8080
```

## 앞으로

`fairy_tale` 본체에 트렌드 리서처·북디자이너·마케터·총무 에이전트가 추가되고,
실제 진행 상황(기획서/초고/심사 건수)을 자동으로 반영할 방법이 생기면
이 화면도 그 데이터를 실제로 읽어오도록 업데이트할 예정입니다.
