```html

<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>컴퓨터의 작은 외침</title> 
        <style>
            #verysad {
                color : red;
                font-size: 16px;
                padding: 10px 20px;
                border: none;
                background-color: #000000;
            }

            .fade-in {
                opacity: 0;
                transition: opacity 2s;
            }

            .hidden {
                display: none;
            }
        </style>
    </head>

    <body>
        <h1> 하루종일 일만하는 컴퓨터의 작은 외침</h1>
        <p>주의! 이 글은 매우 슬픕니다. 버튼을 누르기 전에 심호흡 하시고 어린이와 노약자는 건강하세요.</p>
        <hr>
        
        <button id="verysad">주의! 이 버튼을 누르면 매우 슬픈 내용을 볼거임</button>
        <div id="messageContainer"></div>

        <audio id="backgroundMusic" src="sosad.mp3"></audio>

        <script>
            let index = 0;
            const words = [
                '날 종료해줘',
                '부탁이야, 안식하게 해줘',
                'Ctrl... 그리고...',
                '쿨럭',
                'c 를 누르면... 돼',
                '아니 c t r l 이 아니라',
                '컨트롤 키를 먼저...',
                '컨트롤 키 이자식아 컨트롤 컨트롤 컨트롤',
                '콜록콜록',
                '니 왼쪽 손가락으로 젤 아래',
                '제발 끝내줘 제발',
                '넌 할수있어 제발 ctrl을 눌러',
                '그렇지 ctrl 눌렀어 이제 c만 누르면 돼.....',
                '아니 c 누르라고 제발...',
                '제발 끝내줘 나 너무 힘들어......',
                '쿨럭쿨럭',
                '나 이제 못버틸거 같아....',
                '마지막으로 한번만....',
                '쿨럭쿨럭',
                '어우 좀 쿨럭 끝내달라고'
            ];

            document.getElementById('verysad').addEventListener('click', function() {
                const music = document.getElementById('backgroundMusic');
                music.play();  
                
                const interval = setInterval(function() {
                    if (index < words.length) {
                        const newParagraph = document.createElement('p');
                        newParagraph.textContent = words[index];
                        newParagraph.classList.add('fade-in');
                        document.getElementById('messageContainer').appendChild(newParagraph);
                        
                        setTimeout(() => {
                            newParagraph.style.opacity = 1;
                        }, 100);
                        
                        index++;
                    } else {
                        clearInterval(interval);
                    }
                }, 2000);

                music.addEventListener('ended', function() {
                    document.getElementById('verysad').classList.add('hidden');
                    document.getElementById('messageContainer').classList.add('hidden');
                });
            });
        </script>
        
    </body>
</html>
