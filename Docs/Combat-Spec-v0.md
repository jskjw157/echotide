# ECHOTIDE Combat Spec v0 (Prototype)

목표: 명조식 손맛 - 회피/패링/교대 3박자. PC 60fps 프로토타입 기준.

## 1. 팀 구성
- 3인 1팀, 필드 1명만 조작. 나머지 2명은 백그라운드에서 Concerto(협주) 게이지 충전.
- 교대 쿨타임: 6s. 교대 시 Intro Skill 발동 (입장 딜/버프), 퇴장 시 Outro Skill 잔류.

## 2. 기본 조작 (키보드+패드)
- 약공격 x4 콤보 (4타에 강인성削), 강공격 홀드 차지
- 점프 x2단, 공중 공격 x3
- 회피: Shift, 무적 0.35s. Just Dodge(피격 0.15s 전) 성공 시 슬로모 0.6s + 반격창
- 패링: 마우스우클릭, 판정 0.25s. 성공 시 적 경직 1.2s + Concerto +25
- 스킬(E): 쿨 12s. 궁극(Liberation): Tide 게이지 100 소모
- 교대: 1/2/3 or 휠. QTE 교대: 적 패링 성공 시 2s 내 교대하면 추가 Intro 강화

## 3. 에코(잔향) 시스템 - v0 간소화
- 정예 이상 처치 시 30% 확률로 Remnant 드롭
- 장착: 1인당 Remnant 1개만 (코스트 개념은 v1에서)
- 사용키 T: 변신기/소환기 1회. 예: 울프형 돌진, 비행형 포격
- 등급: C/B/A/S, 스탯은 공격%/크리만 (복잡한 옵션은 나중에)

## 4. 적 AI v0
- 패턴 3종: 근접 2연격(패링 가능), 돌진(회피 유도), 원거리 투사체(패링 가능)
- 강인성(Poise) 게이지: 패링/강공으로削, 0 되면 그로기 3s
- 보스 1종: HP 20k 기준, 페이즈 없음 (v1에서 2페이즈)

## 5. 수치 v0 (테스트용)
- 캐릭터 HP 5000, ATK 450, DEF 300, 크리 50%/100%
- 약공 배율: 60/70/80/120%, 강공 200%, 스킬 350%, 궁극 800%
- 적 잡몹 HP 3000, 정예 8000, 보스 20000

## 6. 구현 순서 (UE5)
1. ThirdPerson + EnhancedInput + Camera lock-on
2. Attack combo + Hitstop/Hit spark (GameplayAbility or custom)
3. Dodge i-frame + slow-mo (SetGlobalTimeDilation 0.3)
4. Parry check via trace + enemy telegraph UI
5. Swap Intro/Outro + Concerto UI
6. Remnant capture/use (DataAsset + SpawnActor)
7. Dummy Boss arena in /Content/Maps/Arena_01

## 7. 제외 (v0에서 안 함)
- 오픈월드, 멀티, 가챠, 육성, 코옵, 모바일 최적화
