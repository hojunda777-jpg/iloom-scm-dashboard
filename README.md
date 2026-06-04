# iloom SCM 대시보드 (외부망 통합 페이지)

일룸 SCM팀 운영 대시보드의 외부망 배포용 정적 사이트입니다.

**URL: https://hojunda777-jpg.github.io/iloom-scm-dashboard/**

## 구성

| 경로 | 시트 | 상태 |
|------|------|------|
| `/spec-change/` | 사양변경 관리 | Live |
| `/outlet/` | 아울렛 재고 현황 | Live |
| `/new-product/` | 신제품 분석 | Live |
| `/cumulative/` | 누적재고관리 | Live |
| `/supply/` | 공급량 관리 | Live |
| `/sku-status/` | 운영품목 현황 | Live |
| `/scp/` | SCP 실적현황 | Live |

## 갱신

내부 PC에서 다음을 실행하면 7개 시트가 모두 재생성되어 GitHub Pages에 푸시됩니다.

```bash
python build_all.py
```

`/morning` 스킬 실행 시 자동으로 호출되도록 설정되어 있습니다.

## 데이터

- **소스**: 사내 MS SQL `fgdw` (재고/수주/출고 등) + BigQuery `iloom-scm.inventory.*` (계획·예측)
- **갱신 주기**: 매일 오전 (사용자 morning 루틴 시점)
- **기준일자**: 각 페이지 우측 상단에 표시
