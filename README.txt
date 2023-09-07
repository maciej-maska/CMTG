Należy uruchomic:

docker-compose up

(Na office trzeba to zrobić przez "sudo" i musi chodzic service "docker")

a nastepnie skopiowac zawartosc katalogu "_site" do tartarus:/var/www/html/cmtg/

Office: 

rsync -arvz -e 'ssh -p 2022' --progress _site/ tartarus:/var/www/html/cmtg/

Zmniejszenie ikon "social": _sass/_base.scss 
.contact-icons {
    font-size: 2rem;  (było 4rem)

Usunięty blog i submenus (_pages/dropdown.md: nav: false)

Dołożone logo do stron _layouts/about.html:
        <h1 class="post-title">
            <div style=”clear: both” >
              <img style="display: inline-block; vertical-align: middle; padding-right: 10px; margin-bottom: 0px; margin-top: 8px; float:left; width: 130px" src="{{ 'CMTG_logo0.png' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
            </div>       
            {% if site.title == "blank" -%}<span class="font-weight-bold">{{ site.first_name }}</span> {{ site.middle_name }} {{ site.last_name }}{%- else -%}{{ site.title }}{%- endif %} 
        </h1>
oraz _layouts/page.html:
        <h1 class="post-title"><img style="display: inline-block; vertical-align: 8px; padding-right: 10px; margin-bottom: -11px;" src="{{ 'CMTG_logo3.png' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">{{ page.title }}</h1>