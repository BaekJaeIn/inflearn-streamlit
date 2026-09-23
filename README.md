# 소득세 RAG 챗봇

인프런 강의 **「RAG를 활용한 LLM Application 개발」**을 따라 만들며 학습한 프로젝트입니다. Streamlit 채팅 화면에서 소득세 관련 질문을 입력하면, Pinecone에 저장된 문서를 검색해 OpenAI 언어 모델이 답변합니다.

## 주요 기능

- 대화형 소득세 질의응답 UI
- 대화 맥락을 반영한 질문 재작성 및 문서 검색
- 검색 결과와 예시 답변을 활용한 RAG 응답 생성
- 응답 스트리밍 표시

## 사용 기술

- Python, Streamlit
- LangChain
- OpenAI Chat Completions 및 임베딩
- Pinecone 벡터 데이터베이스

## 실행 방법

1. Python 3.11 환경을 준비하고 의존성을 설치합니다.

   ```bash
   pip install streamlit python-dotenv langchain-core langchain-classic langchain-openai langchain-pinecone langchain-community
   ```

2. 프로젝트 루트에 `.env` 파일을 만들고 아래 환경 변수를 설정합니다.

   ```env
   OPENAI_API_KEY=your-openai-api-key
   PINECONE_API_KEY=your-pinecone-api-key
   ```

3. Pinecone에 `tax-markdown-index` 인덱스를 준비하고, 검색에 사용할 소득세 문서를 적재합니다. 인덱스와 문서가 준비되지 않으면 검색 체인을 실행할 수 없습니다.

4. 앱을 실행합니다.

   ```bash
   streamlit run chat.py
   ```

## 프로젝트 구성

- `chat.py`: Streamlit 채팅 UI
- `llm.py`: LLM, 대화 이력, 검색기 및 RAG 체인
- `config.py`: few-shot 예시 답변

## 참고

이 저장소는 강의를 따라 만든 학습용 프로젝트입니다. 생성형 AI 답변은 참고용이며, 실제 세무 판단에는 최신 법령과 전문가의 확인이 필요합니다.
