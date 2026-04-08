# Playbooks — hotel-price-compare

> CLI command sequences. Knowledge is for parameter mapping — never answer without executing.

---

## Playbook A: Price vs Rating

**Trigger:** "compare hotels", "对比酒店"

```bash
flyai search-hotel --dest-name "{city}" --sort price_asc --check-in-date {in} --check-out-date {out}
flyai search-hotel --dest-name "{city}" --sort rate_desc --check-in-date {in} --check-out-date {out}
```

**Output emphasis:** Two searches: cheapest + best rated, merged into comparison table.

---

## Playbook B: Star Category Compare

**Trigger:** "3-star vs 4-star"

```bash
flyai search-hotel --dest-name "{city}" --hotel-stars 3 --sort price_asc --check-in-date {in} --check-out-date {out}
flyai search-hotel --dest-name "{city}" --hotel-stars 4 --sort price_asc --check-in-date {in} --check-out-date {out}
```

**Output emphasis:** Compare price gap between star levels.

---

## Playbook C: Value Score

**Trigger:** "best value hotel"

```bash
flyai search-hotel --dest-name "{city}" --sort rate_desc --check-in-date {in} --check-out-date {out}
```

**Output emphasis:** Calculate value score = rating / price.

---

