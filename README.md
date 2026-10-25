# 용접 단위길이 입열량 계산기

일정한 전압·전류·이동속도에서 전기 아크 에너지 중 모재에 전달되는 길이당 열량을 구합니다.

- ID: E159
- App: https://nanalab.kr/eng-welding-line-heat/
- Repository: https://github.com/NaNaCompany/eng-welding-line-heat
- Formula: H = ηUI/v; 1 kJ/mm = 10⁶ J/m

## Model and data

일정한 전압·전류·이동속도와 공정에 맞게 정한 열효율을 가정합니다. η=1이면 보정 전 아크 에너지/길이입니다. 펄스·교류처럼 전압과 전류가 변하면 평균 전압×평균 전류가 평균 순간전력과 다를 수 있어 이 식을 그대로 적용하지 마세요. 열영향부 온도·냉각속도·용접 적합성은 계산하지 않습니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
