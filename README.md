# first-homework

##html-head태그
1. `<link rel="icon" href="https://www.youtube.com/s/desktop/e436da45/img/favicon_144x144.png">`을 삽입한 이유는 브라우저 탭 title 옆에 아이콘 그림을 넣기 위해서입니다.

##html-body태그
1. body태그는 .fixed들과 main태그로 나뉘어져있습니다.
.fixed태그가 2개인 이유는 뷰표트 위에 붙어야하는 header과 nav부분과 따로 옆에 붙어있는 aside부분이 .fixed태그 하나로 묶여져 있으면 aside부분의 높이와 header부분의 너비의 박스가 .fixed로 취급되기 때문입니다.
.fixed는 css에서 display:fixed로 고정됩니다.
2. 우선 position:absolute를 사용할 일이 생길 수 있으니 position:relative를 넣어줍니다.
3. 그리고 display:grid를 넣어 header와 nav와 aside를 나눠줍니다. main은 동영상이 업로드 됨에 따라 길이가 길어질 수 있으므로 main은 grid를 넣어주지 않았습니다.
4. reset.css를 넣어주면 line-height가 너무 낮으니, 18px로 줄 사이에 길이를 줍니다.
5. 화면이 너무 좁으면 홈페이지를 보기 힘들어지니, min-width를 넣습니다.
###html-body-.fixed태그
1. .fixed태그는 header+nav로 묶여진 클래스와 aside로만 이루어진 클래스로 존재합니다.
2. .fixed가 메인에 가려지는 스크롤을 내릴 때 main에 가려지는 일이 없도록 z-index:1을 넣어줍니다.
3. .fixed는 display:fixed로 설정해줍니다. z-index는 display가 있을 때(기본값이 아닐 때) 사용될 수 있습니다.
####html-body-.fixed-.header태그
1. .header태그는 `.list_logo`태그와 .search태그와 `.user_name`태그로 이루어져 있습니다.
2. .header, .nav, .aside, .main은 중간에 비어진 부분이 존재하지 않으므로 display:flex로 작업해줍니다.
3. box-sizing이 기본값인 content-box일 경우, 계정사진이 넘어가 보이지 않는 경우가 발생하니 border-box로 바꿔줍니다.
#####html-body-.fixed-.header-`.list_logo`태그
1. `.list_logo`클래스는 .list클래스와 `.logo_locate`클래스로 이루어져 있습니다.
	1. align-items:center값이 없으면 list가 위로 올라가는 현상이 발생하니 넣어줍니다.
2. .list클래스는 백터이미지인 svg를 사용했습니다.
	1. click이 되므로 cursor:pointer을 넣어줍니다.
	2. svg이미지는 css로 조절할 수 있습니다.
3. `.logo_locate`클래스는 .logo클래스와 .locate클래스로 이루어져 있습니다.
4. .logo클래스도 svg이미지로 이루어져있습니다.
5. .locate클래스는 위첨자태그인 sup를 사용했으며, 지역을 나타내는 문구가 적혀져 있습니다. 저는 유튜브 코리아를 참조해 만들었으므로 KR이 적혀져 있습니다.
#####html-body-.fixed-.header-.search태그
1. .search클래스는 `.search_bar_button_keyboard`클래스와 `.rec_search`클래스로 이루어져 있습니다.
	1. .search클래스가 뷰포트가 작아질 때, 양쪽 그리드에 침범되지 않도록 min-width를 넣어줍니다.
2. `.search_bar_button_keyboard`클래스는 `search_bar`클래스와 keyboard클래스, `.search_button`클래스로 이루어져 있습니다.
	1. `.search_bar_button_keyboard`클래스는 높이가 `.search_button`과 동일해야하므로 height:max-content로 넣어줍니다.
3. `search_bar`클래스는 input태그로 기본값인 text를 사용했고, 입력이 되지 않았을 경우, "검색"이라는 글씨가 보일 수 있도록 placeholder값을 "검색"으로 넣어뒀습니다. 글자수 제한은 넣어두지 않았습니다.
	1. `.search_bar`클래스에 min-width:0을 넣어두지 않으면 `.rec-search`클래스가 `.search_bar`클래스까지 침범합니다.
4. .keyboard클래스는 css에서 background-image가 들어가져 있는데, input태그 내에 있는 키보드 그림을 넣기 위해 만들어뒀습니다.
	1. background-repeat:no-repeat이 없으면 사진이 반복됩니다.
	2. 호버링했을 때, 키보드가 변할 수 있도록, :hover가상선택자를 넣어줍니다.
5. `.serach_button`클래스는 input태그 옆에 붙게 됩니다.(.keyboard클래스가 input태그 안으로 들어가게 됩니다.)
	1. flex-shrink:0가 없으면 뷰포트의 너비가 줄어들 때, 버튼이 점점 작아집니다. 
6. 그리고 `.search_bar_button_keyboard`와 약간 떨어진 곳에 `.rec_search`클래스가 존재합니다.
	1. `.rec_search`클래스는 둥근 모양이므로 border-radius:50%를 넣어줍니다. 그럼 온전한 원모양이 됩니다.(너비와 길이가 다르면 타원형이 됩니다.)
#####html-body-.fixed-.header-`.user_menu`태그
1. `.user_menu`태그는 .video태그와 .notice태그, .account태그로 이루어져 있습니다.
2. .account태그에는 본인계정의 프로필 사진이 올라가게 됩니다.
3. 마우스를 호버링 했을 경우 설명으로 "만들기"나 "알림"같은 글씨가 뜨도록 title 내에 "만들기"나 "알림"을 적어줍니다.
4. .account클래스는 img태그를 걸어줍니다.
####html-body-.fixed-.nav태그
1. nav태그 내에 약간 둥근 회색 네모 내에 게임, 음악, 실시간 등의 단어들이 적혀져있습니다. 위의 글씨들을 div태그로 각각 넣어줍니다.
	1. nav는 너비가 aside의 너비인 240px을 제외한 뷰포트 너비이므로, 단위에서 단위를 뺄 때, 사용하는 함수 calc();를 사용합니다.
	2. nav의 위와 밑에는 줄이 그어져 있으므로 border-bottom과 border-top을 사용합니다.
	3. nav를 넘어간 div는 양쪽의 화살표단추를 눌러야 넘겨볼 수 있으므로 , js를 설정해주기 전에는 overflow:hidden을 설정해줍니다.
	4. position:relative와 left:240px이 없으면 nav가 aside와 겹쳐집니다.
	5. white-space:nowrap이어야 뷰포트의 길이가 줄어들 때, div가 줄어들지 않고, 밑에 줄로 내려가는 일이 없어집니다.
2. '전체'는 현재 '전체'에 있다는 뜻으로 검은 네모 내에 있습니다. 현재 있다는 뜻으로 클래스에 on을 넣어줍니다. 자바스크립트를 넣을 경우 classList를 사용해 on을 click하는 div에 넣어줄 수 있게 합니다. 따라서 nth로 css를 넣으면 안됩니다.
3. 뷰포트가 줄어들면 nav의 div들 중 몇개가 보이지 않는 현상이 나타나게 됩니다. 그 경우, nav의 오른쪽이나 왼쪽에 nav를 오른쪽이나 왼쪽으로 이동할 수 있게 도와주는 버튼들이 나타나게 됩니다. .next클래스가 그 경우 오른쪽으로 이동할 수 있게 도와주는 버튼입니다. 평소에는 보이지 않다가 뷰포트가 작아지면 보일 수 있도록 설정해주기 위해서 평소에는 css에서 display:none을 넣어줍니다.
####html-body-.fixed-.aside태그
1. .aside태그는 제가 list메뉴를 열고 따라했기 때문에 list메뉴가 펼쳐진 상태입니다.
	1. .aside의 높이는 haeder의 높이인 56px이 빠진 100vh입니다.
	2. .aside 내부 내용은 높이 안에 다 들어가지 않기 때문에 overflow:auto를 넣어 뷰포트 밑으로 넘어간 내용도 읽을 수 있게 했습니다.
	3. .aside의 자식div만 줄이 그어져 있어야하므로, `.aside>div`로 작업해야 합니다.
	4. li에 display:flex으로 작업해둔 이유는 svg파일과 이름인 div파일이 옆으로 나란히 있어야 하기 때문입니다.
	5. .des에 text-overflow: ellipsis는 .des의 말이 너무 길어질 때, 말줄임표를 넣기 위함입니다.
	6. li.ul-title은 aside의 소제목이므로 클릭이 가능한 부위가 아닙니다. 따라서 cursor:pointer이면 안됩니다. 커서를 원상복구로 만들기 위해서 pointer-events: none으로 설정했습니다.
2. 뷰포트의 가로너비가 줄어들면 list메뉴가 사라집니다. 따라서 @media로 관련 내용을 적어넣었습니다.
3. aside에서 호버링 되는 메뉴가 있고, 분류의 하나로 호버링 되지 않는 메뉴가 있습니다. 그리고 호버링 되지 않는 메뉴 위에는 줄이 그어져 있습니다. 따라서 저는 .aside클래스를 .list-1부터 .list-6까지 나누고, 버튼들 가장 밑에 적힌 글을 따라 적었습니다. 문장이므로 p태그를 넣었습니다. 그리고 몇몇 단어들은 하이퍼링크가 걸려있어서 a태그를 넣었습니다.그리고 a태그 중 몇 단어들은 푸른 글씨로 적혀져 있기때문에 css에서 style태그를 넣기 위해 class로 blue를 넣었습니다.
###html-body-.main태그
1. .main태그는 여러 개의 .video클래스들로 이루어져 있습니다.
2. 높이는 계속 업로드되는 동영상의 수에 따라 달라지므로 height:fit-content를 넣어줍니다.
3. .video가 오른쪽으로 넘어가지 않게 하기 위해 flex-wrap:wrap으로 넣어줍니다.**
4. grid-area가 없으면 자꾸 위치가 넘어갑니다. 이유는 잘 모르겠습니다. 조금 더 공부해 보겠습니다.**
####html-body-.main-.video태그
1. .video태그는 크게 2부류로 나뉩니다. 첫째는 광고고 두번째는 일반적인 비디오파일입니다. 대신, 비디오파일의 크기와 .video클래스가 차지하는 상자의 크기는 동일합니다.
2. 우선 광고 비디오는 일반적인 비디오와는 안쪽 태그가 약간 다릅니다. 광고비디오는 일반 비디오와는 달리 비디오파일 하단에 .title-list클래스를 달아두었습니다. 광고비디오는 광고주의 프로필사진이 들어가있지 않았고(들어가는 경우도 있었지만, 내가 클론코딩할 때는 없었습니다). 대신 타이틀이 약간 더 길었습니다. 그리고 비디오파일에서는 비디오사진 위에 호버링 했을 때, 불투명한 검은 색이 씌워지면서 svg파일과 공유하기라는 글씨가 나왔기 때문에 .ad-hover클래스를 넣어주었습니다.
	1. svg코드의 색깔은 color로 지정하는 것이 아니라 fill로 넣습니다.

3. 광고비디오는 .video-img-time과 img태그까지는 동일하지만, 광고비디오에는 시간이 기록되어있지 않아서 .video-time클래스와, 호버링하면 비디오시간 위에 나타나는 .hover클래스를 제거하고, 일반적인 광고비디오사진 위에서 나타나는 공유아이콘을 .ad-share클래스로 넣고, 광고비디오사진 호버링 시 나타나는 "구독하기"와 아이콘버튼을 .ad .ad-hover클래스로 넣었습니다.
4. 광고비디오에서 비디오이미지파일이 아닌 글로 이루어진 부분은 .title-list클래스로 넣었습니다. 우선 .title클래스는 다른 광고일 경우에는 길고 짧아지는 경우가 발생할 수 있으니, span태그로 넣고 일반 광고들이랑 다르게 비디오 내의 list메뉴가 항시 보여지고 있으니 .list클래스로 작성했습니다. 그리고 작은 글씨로 적혀진 광고 내용을 적고, 그 밑에 광고를 표시하는 문구와 광고회사가 들어갑니다. 광고회사도 회사마다 글자의 길이가 달라질 수 있으니, span태그로 넣었습니다. 5. 일반비디오는 비디오시간이 기본적으로 나오므로 .video-time클래스를 넣었습니다. 비디오시간도 역시 달라질 수 있으니 span태그로 넣었습니다. 그리고 비디오사진 파일을 호버링했을 경우 시간이 가려지고, 계속마우스를 오버하여 재생하기라는 문구가 나올 수 있도록 .hover클래스를 넣었습니다.
일반비디오의 .account-title계정에는 비디오를 올린 계정의 사진이 나오도록 .video-account클래스를 넣었습니다. 그리고 .video-title클래스에는 .title클래스를 넣었습니다. .title의 길이 역시 각기 다를 수 있으므로 span태그를 사용했습니다. 그리고 비디오의 올린 계정의 닉네임과 비디오 조회수, 올린 날짜를 나올 수 있게 만들어뒀습니다. 이 역시 글자 수에 따라 달라질 수 있으므로 span태그를 사용했습니다.


[원본]: https://www.youtube.com/
[제작본]: https://warm-heliotrope-0c2d30.netlify.app/
