# grounding-cache
LLM grounding API 를 사용했을 때 캐싱하는 구조 구현
- 아래 오픈소스에 캐싱을 추가하는 테스트
https://github.com/google-gemini/gemini-fullstack-langgraph-quickstart

## 필요성
- LLM 검색어 생성 -> grounding 구조를 구현할 경우, 과금 때문에 웹서치 요청에 대해 캐싱이 필요하다. 
- Gemini grounding API 은 1500번 호출에 35$ 정도 과금된다.
- 에이전트 서비스에 대용량 트래픽이 가해질 경우 이 부분이 문제될 수 있다.

## 테스트
- 유사한 주제 (예: 가성비 제품 추천) 에 대해 사용자가 입력할만한 input set 을 생성하고, 에이전트 내의 파라미터 (예: 서치 키워드 수, 기간, 검색어 생성 프롬프트 등) 를 튜닝하면서 테스트한다.
- 캐시 hit rate 가 얼마나 되는지