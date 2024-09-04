## 1. 프로젝트 소개
#### 1.1. 개발배경 및 필요성
- 개발 배경
  > 양산시에 위치한 부산대학교 양산캠퍼스 학생들은 매일 즐거운 학교생활을 보내는 나머지 하루하루 금전난에 시달리고 있다. 식비와 생활비부터 동아리 회비와 수업교재 값 까지 학생들은 많은 비용을 지출하게 된다. 이러한 이유로 많은 학생들이 학기 중임에도 알바를 구하려 하는 추세를 보인다. 이때 학생들은 주로 알바 구직 어플을 사용한다. 이 과정에서 우리는 더 효율적인 알바 어플을 구현할 수 없는지에 대한 의문이 생겼다.

- 개발 필요성
  > 일반적인 알바 구직 어플은 알바의 종류와 시간대, 그리고 임금 정도의 정보만을 제공하고 있다. 하지만 학기 중에 알바를 구하는 대학생의 경우에는 수업 시간이나 동아리 활동 등 고려해야 할 점이 더 많다. 따라서 우리 팀은 이러한 번거로움을 해결하기 위해 기존의 알바 어플 구직 어플에서 나아가, 대학생 개개인의 학업 및 스케쥴을 고려한 맞춤 알바 매칭어플을 개발하고자 한다.

#### 1.2. 개발목표 및 주요 내용
- 개발목표
  > 대학생의 학업 시간표를 입력받아 이를 분석하여 구하고자 하는 알바의 시간대와 겹치지 않도록 확인하고, 알바 시급 또는 장소를 포함하여 알바를 추천해주는 알고리즘을 개발하고자 한다. 또한, 양산에서 알바를 구하고자 하는 사업자들의 협력을 통해 여러 알바 정보를 제공한다. 우리가 개발할 앱을 통해 부산대학교 양산캠퍼스에 재학중인 학생들이 알바를 더욱 간편하게 구하고, 학업과 알바의 균형을 맞추는데 도움을 주고자 하며, 지역사회의 경제 활성화에도 기여하는 것이 이 프로젝트의 최종적인 목표이다.

- 주요 내용
  > 먼저, 앱을 실행하면 ID와 PW를 입력하는 로그인창이 띄워지도록 한다. 이때, 계정등록이 안되어있다면, 회원가입하는 창도 만든다. 회원가입은 ID와 PW, 앱 내에서 사용할 닉네임을 작성하는 칸이 있고, 작성 후 본인 명의를 확인한다. 회원가입이 되면, 회원의 정보를 앱의 클라우드에 저장하고, 이후 로그인을 할 때마다 클라우드에서 회원의 정보와 일치하는지 확인하게 된다.
최초 로그인 이후, 생년월일, 성별, 학과, 학년 등을 작성하는 개인정보 작성란을 띄운다. 필수적으로 등록해야 하기에, 작성을 하지 않는다면 다음 화면으로 넘어가지 않는다. 작성을 완료했다면, 사용자의 개인정보도 앱의 클라우드에 저장된다.

  > 또한, 알바를 구인하고자 하는 사업자의 경우, 사업자 항목에 체크하고, 사업자 인증을 추가로 진행한다.
이제, 사용자의 학업 시간표를 등록하는 창을 띄운다. 학업 시간표의 경우, 월금까지 오전 9시부터 오후 5시까지의 빈 시간표에서 자신이 듣는 수업의 시간을 등록할 수 있다. 시간표 등록의 편의를 위해 앞에서 작성한 개인정보를 이용해 학과별, 학년별 전공기초나 필수교양들을 선택할 수 있도록 한다. 이외의 교양선택이나 일반선택과 같은 수업들은 1영역부터 8영역까지의 영역을 선택하여 그 안에서 자신이 듣는 수업을 선택할 수 있도록 한다. 이외에도 동아리와 같은 개개인의 매주 루틴을 작성하여 추가할 수 있도록 하여 시간표를 완성한다.

  > 사업자의 경우, 자신의 사업장, 시급, 기간, 요일, 모집 조건과 같은 알바 구인 정보를 작성할 수 있도록 한다. 이때 들어가야 할 모집 조건은 모집 마간 기한, 모집 인원, 성별, 연령, 학력, 우대 사항 등이 있다. 근무조건은 급여, 근무기간, 근무요일, 근무시간, 직종, 고용형태(알바나 계약직), 복리후생 등이 있다.

#### 1.3. 세부내용
- 시간표 시스템
  > 사용자는 알바노에 있는 시간표에 자신의 스케줄을 pnu, 기타, 알바, 비는 시간 이렇게 네 가지 유형으로 기록할 수 있으며, 각 유형들은 고유의 지정색을 가진다. 사용자가 기록한 스케줄에 따라 시간표에서 해당 시간의 칸이 지정색으로 칠해진다. 부산대학교 관련 시간인 pnu는 사용자가 부산대학교 연동 버튼을 클릭했을 때 부산대학교에 있던 사용자의 수업 시간표에 따라 알바노 시간표의 해당 칸들에 자동으로 지정색이 칠해진다.
  
  > 사용자는 자유롭게 시간표를 수정할 수 있으며, 이로써 사용자는 자신의 시간표에서 pnu, 기타, 알바 시간의 분포와 빈 시간들을 한눈에 확인하게 된다. 
 이렇게 만들어진 시간표는 사용자의 스케줄에서의 빈 시간 정보를 추출하게 된다. 이 정보를 사용하여 사용자의 스케줄에 맞는 알바를 분류해낸다.
- 로그인 시스템
  > 사용자는 부산대학교 공식 웹사이트에 사용하는 계정으로 앱에 로그인할 수 있다. 사용자는 자신의 학번과 비밀번호를 입력하여 알바노에 로그인하게 된다. 동시에 이는 알바노에서 아르바이트 구직을 위해 필요한 정보인 사용자의 시간표와 신원 정보가 부산대학교에서 알바노에 연동됨을 의미한다.
  > 
- 검색 시스템
  > 검색창에 입력된 키워드가 포함된 내용의 아르바이트를 창에 띄워준다. 근무를 원하는 지역과 반경을 선택할 수 있으며, 상세조건 추가와 키워드 제외를 통해 근무지역, 직종, 근무기간, 고용형태를 한정한다. 기존에 연동한 시간표를 불러와 수업, 동아리 등 아르바이트 근무를 할 수 없는 시간을 제외하여 검색한다.

  > 검색창에 키워드를 입력하지 않아도 이전 검색 결과를 토대로 한 맞춤 검색어 기능을 이용할 수 있으며, 어플 사용자들의 사용 현황을 종합해 매 시간 업데이트한 인기 검색어를 볼 수 있다.

  <details>
      <summary>이미지 보기</summary>
      <img src="https://ifh.cc/g/T21kgK.png" alt = "설명">
    </details>
- 알바 추천 시스템
  > 아이템 기반 추천 (Item based Recommandation)을 이용하여 사용자가 이전에 확인한 알바를 기반으로 해당 알바와 유사한 다른 알바를 추천하는 방식을 채택하였다. 알바 간의 유사도는 알바에 할당되어 있는 태그에 각각의 가중치를 매겨 측정하였다.

#### 1.4. 기존 서비스 대비 차별성
  - 대학생들에게 최적화된 구직 방법
    > 알x몬과 같은 기존의 알바 구직 어플과는 달리, 시간표 연동이라는 기능을 이용하여 시스템 상에서 자동으로 시간표 내의 수업시간을 제외한 알바들을 검색해준다.
    <details>
      <summary>이미지 보기</summary>
      <img src="https://ifh.cc/g/qWwvlP.png" alt = "설명">
    </details>

#### 1.5. 사회적가치 도입 계획
  - 부산대학교 학생들의 구직을 장려함으로써 학업의 금전적 어려움을 해결한다.
    > 전공과 적성에 따라 복잡한 학업 스케줄을 가진 대학생들이 비는 시간을 일일이 검색해야 하는 수고로움을 덜어주어 구직 활동을 장려한다. 생활비와 교재비 등의 금전적 어려움을 아르바이트 활동으로 해결하여 정서적 만족감을 얻고, 주체적인 대학 생활을 이끌어낸다.

## 2. 상세설계
#### 2.1. 사용 기술
  - Saramin API
  - Flutter (Channel Stable, 3.24.1)
  - Figma

## 3. 개발결과
#### 3.1. 전체시스템 흐름도
  > IA 정보구조도
    <img src="https://ifh.cc/g/pBxplW.png" alt = "설명">
  
#### 3.2. 기능 설명
###### 3.2.1 로그인
  > 아이디, 비밀번호를 입력한 후 계정이 있는지 확인한다. 계정이 없으면 경고문구가 나타나고, 계정이 있는 경우 로그인이 성공한다.
<img src="https://ifh.cc/g/66pCJc.png" alt = "설명">

###### 3.2.2 홈 화면
  > 홈 화면에서는 현재 거주중인 지역과 추천 알바, 최근 지역공고를 모아볼 수 있다. 지역은 부산광역시와 양산시 내에서 선택할 수 있다.
<img src="https://ifh.cc/g/6qZ4fP.jpg">

  > 내게 딱 맞는 알바는 사용자가 이전까지 조회한 알바와 즐겨찾기한 알바, 그리고 시간표의 빈 시간을 분석하여 아이템 기반 추천 기능을 사용하여 점수가 가장 높은 6개의 알바를 선정하였다.
<img src='https://ifh.cc/g/ZtWA20.jpg'>

###### 3.2.3 시간표 화면
  > 시간표를 등록하여 수업 또는 개인 시간을 제외한 알바를 추천해준다. 부산대학교 계정으로 로그인이 되어있다면, 시간표 연동을 통해 한 번에 시간표를 입력할 수 있다. 하나하나 입력하는 것 또한 가능하다.
<img src='https://ifh.cc/g/zY4Yo8.png'>
<img src='https://ifh.cc/g/YKgyqD.png'>

> 실행 화면 예
<img src ='https://ifh.cc/g/79G8qz.png'>
<img src ='https://ifh.cc/g/ma7Cft.png'>

###### 3.2.4.1 검색 화면
  > 특정 키워드를 이용하여 검색할 수 있는 검색화면이다. 최근 검색한 내용들을 보여주며, 최근 검색어를 이용해 아이템 기반 추천 알고리즘으로 맞춤 검색어 또한 추천해준다. 실시간 여러 유저들의 검색어 트래픽을 이용하여 인기 검색어를 1부터 10등까지 순위로 보여주는 기능 또한 있다.
<img src='https://ifh.cc/g/1bzOvj.png'>

###### 3.2.4.2 검색 결과 화면
  > 검색한 결과가 나타나는 화면이다. 필터링 기능을 이용하여 지역과 상세 조건을 필터링할 수 있으며, 등록날짜에 따라 오름 또는 내림차순으로 정렬하는 것이 가능하다. 결과에 표시된 알바의 지원하기를 누르면 온라인 지원창으로 이동한다.
<img src='https://ifh.cc/g/1DyCOl.png'>

###### 3.2.5 온라인 지원
  > 온라인으로 지원할 수 있는 화면이다. 현재 지원하려는 알바가 무엇인지, 사용자의 정보를 확인할 수 있고, 이력서 선택을 통해 미리 적어놓은 이력서를 그대로 첨부할 수 있다. 마지막으로 각오 한마디를 써서 개인적인 어필을 할 수 있다.
<img src='https://ifh.cc/g/ApBly5.png'>

#### 3.3. 기능명세서
Compact modeLine breaks as <br>
Result (click "Generate" to refresh) Copy to clipboard  Preview
| 화면       | 세부페이지     | epic          | 기능               | 부가설명                                                                                    | 구현여부 | 디자인여부 |   |
|------------|----------------|---------------|--------------------|---------------------------------------------------------------------------------------------|----------|------------|---|
| 로그인     | 학생로그인     | 회원관리      | 아이디입력         | 틀릴 경우 "아이디와 비밀번호가<br>맞는지 확인해주세요" 띄우기<br>맞을 경우 홈 화면으로 이동 |          |            |   |
|            |                |               | 비밀번호입력       |                                                                                             |          |            |   |
|            | 사업자로그인   |               |                    |                                                                                             |          |            |   |
|            |                |               |                    |                                                                                             |          |            |   |
|            |                |               | 비밀번호찾기       | 아이디(전화번호)입력과 인증으로 새 비밀번호 설정가능                                        |          |            |   |
|            | 사업자가입     |               | 아이디인증         | 전화번호와 사업자인증                                                                       |          |            |   |
|            |                |               | 비밀번호설정       | 조건 : 8자이상 영문 + 숫자 조합                                                             |          |            |   |
| 홈         | 검색           | 알바추천      | 검색어             | 맞춤검색어추천                                                                              |          |            |   |
|            |                |               | 카테고리검색       | 알바유형별추천                                                                              |          |            |   |
|            | 내게딱맞는알바 |               | 알바추천배너       | 근처 대학생우대 알바추천                                                                    |          |            |   |
|            | 최근지역공고   |               | 최신알바           | 최근 등록된 주변알바추천                                                                    |          |            |   |
| 시간표     | 연동하기       |               | 부산대시간표와연동 | 수업시간이 파란색으로 표기됨                                                                |          |            |   |
|            | 수정           |               | 추가/삭제          | 연동된 시간표를 수정하거나 동아리/알바/기타 일정 등록 및 삭제                               |          |            |   |
|            | 맞춤알바추천   |               | 한줄알바추천배너   | 등록된 시간표를 기반으로시간표 하단에 한줄로맞춤알바추천                                    |          |            |   |
| 마이페이지 | 이력서         | 학생정보/편의 | 등록               | 회원정보/학력/경력/개인정보이용동의 등 등록가능                                             |          |            |   |
|            |                |               | 보기               | 등록에서 입력한 정보를 수정 및 삭제가능, 본인사진 등록가능                                  |          |            |   |
|            | 최근본         |               | 최근본 알바배너    | 최근본 알바 모아보기 / 선택지원 및 삭제가능                                                 |          |            |   |
|            | 알림           |               |                    |                                                                                             |          |            |   |
|            | 지원현황       |               |                    |                                                                                             |          |            |   |

#### 3.4. 디렉토리 구조
  > 

## 4. 설치 및 사용 방법
- 안드로이드는 apk 파일을 통해 설치, 실행

## 5. 소개
- <알바고민? 알바노!>
부산대학교 학생을 위한 맞춤 알바 구직 앱 '알바노'.
 내게 딱! 맞는 알바, 이젠 하나하나 찾아볼 필요 없이 알바노에서 확인하세요!
  
  <img src="https://ifh.cc/g/JkqGz1.jpg" width="10%">

## 6. 팀 소개
  - 팀장 윤상현
  - 개발 및 디자이너 조은서
  - 개발 및 디자이너 박선영
  - 개발 및 디자이너 구예미
    
## 7. 해커톤 참여 후기
  - 윤상현 : 이전에도 해커톤에 참여한 적이 있었지만, 플러터나 피그마를 사용한 적은 없었는데, 이번 기회에 처음 사용하게 되어 따로 공부를 하는 데에 많은 시간을 쏟았다. 이 프로젝트를 시작하기 전까지만 해도 프론트 엔드, 백엔드에 대한 지식이 많이 없었지만, 주어진 시간 내에 앱을 완성하기 위해 더 공부를 많이 한 것 같다. 아직 1학년임에도 불구하고 해커톤에 참여하여 본선까지 진출할 수 있어서 좋은 경험이었다.
  - 조은서 : 더 나은 앱을 만들기 위해서 계속 고민하고, 계획한 것들을 실행시키고 어려운 과정도 겪으며 개발에 있어서 정말 많은 공부가 되었고, 의미있는 시간들이었습니다. 앞으로 무엇을 더 배워야 하는지도 깨닫게 되었습니다.
  - 박선영 : 만들고자 하는 것을 구체화하는 과정이 좋은 경험이 되었다. 어플을 디자인하고 구현하는 데에 모르는 것이 많아 미숙했지만, 덕분에 디자인 프로그램을 사용하는 방법이나 코드로 변환하는 방법을 배울 수 있었다. 막연히 뭔가를 만들고 싶다는 추상적 아이디어를 눈에 보이는 것으로 구체화할 수 있다는 면에서 개발의 매력을 느꼈다. 또한 장기 팀 프로젝트인 만큼 맡은 바 역할을 해야 한다는 책임감을 배웠다. 이번 해커톤이 부족한 점을 알고 공부하여 발전하는 계기가 되어 의미깊었다.
  - 구예미 : 처음 지원할 때만해도 아무것도 모르는 새내기였던 제가 팀원들과 개발을 진행해 나가면서 플러터, 피그마, 깃허브 등의 다양한 프로그램에 던져졌고 구르고 포기했다가 다시 들어오길 반복하며 이런 환경에 어느정도 익숙해져 갔습니다. 절대 불가능 할 것만 같던 개발이 점차 윤곽을 갖춰가며 좌절과 두려움 속에서 작은 즐거움과 성취감이 자라갔고 팀원들과 밤을 새는 동안에도 곡소리보단 웃음소리가 더 컸던 것 같습니다. 해커톤 준비를 하며 책임감의 무게를 느끼게 되었고 앱 구동과 디자인 등의 방면에서도 좋은 경험을 쌓을 수 있었습니다. 이번 대회를 통해 느낀바를 토대로 학과공부와 자기개발에 힘써 더 많은 대회에 보다 나은 나로 참여할 수 있었으면 좋겠다는 생각이 들었습니다. 이런 기회를 제안해준 팀원들에게 고맙고 따스한 눈빛과 조언으로 응원해주신 박미현 교수님 사랑합니다.






