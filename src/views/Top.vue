<template>
  <div>
    <!-- Navigation bar -->
    <Header />

    <!-- Head area -->
    <section class="hero is-link is-fullheight is-fullheight-with-navbar">
      <div class="hero-body">
        <div class="container">
          Hello! I am
          <h1 class="title is-1">
            Lima.json
          </h1>
          <h2 class="subtitle is-3">
            Backend Web Developer <br />(API Developer)
          </h2>
        </div>
      </div>
    </section>

    <!-- About -->
    <section class="section" id="about">
      <!-- Title -->
      <div class="section-heading">
        <h3 class="title is-2">About Me</h3>
        <h4 class="subtitle is-5">私について、概要</h4>
        <div class="container">
          <p>
            Web developer with more than <strong>4 years</strong> of
            well-rounded experience with a degree in the field of
            <strong>Computer Science</strong>, extensive knowledge of modern Web
            techniques and love for <strong>Coffee</strong>. Looking for an
            opportunity to work and upgrade, as well as being involved in an
            organization that believes in gaining a competitive edge and giving
            back to the community.
          </p>
        </div>
      </div>

      <div class="columns has-same-height is-gapless">
        <div class="column">
          <!-- Profile -->
          <div class="card">
            <div class="card-content">
              <h3 class="title is-4">Profile</h3>

              <div class="content">
                <table class="table-profile">
                  <tr>
                    <th colspan="1"></th>
                    <th colspan="2"></th>
                  </tr>
                  <tr>
                    <td>Address:</td>
                    <td>Tokyo, Kanagawa</td>
                  </tr>
                  <tr>
                    <td>Phone:</td>
                    <td>secret!!</td>
                  </tr>
                  <tr>
                    <td>Email:</td>
                    <td>lmimsra07@gmail.com</td>
                  </tr>
                </table>
              </div>
              <br />
              <div class="buttons has-addons is-centered">
                <a href="https://github.com/lmimsra" class="button is-link">
                  Github
                </a>
                <!--                <a href="#" class="button is-link">LinkedIn</a>-->
                <a
                  href="https://twitter.com/lmimsra_dev"
                  class="button is-link"
                >
                  Twitter
                </a>
                <!--                <a href="#" class="button is-link">CodeTrace</a>-->
              </div>
            </div>
          </div>
        </div>
        <div class="column">
          <!-- Profile picture -->
          <div class="card">
            <div class="card-image">
              <figure class="image is-4by3">
                <!-- TODO なんか画像入れる -->
                <img
                  src="https://source.unsplash.com/random/1280x960"
                  alt="Placeholder image"
                />
              </figure>
            </div>
          </div>
        </div>
        <div class="column">
          <!-- Skills -->
          <div class="card">
            <div class="card-content skills-content">
              <h3 class="title is-4">Skills</h3>
              <div class="content">
                <SkillBar
                  v-for="(skill, index) in skills"
                  v-bind:key="index"
                  v-bind:skill-name="skill.name"
                  v-bind:skill-level="skill.value"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills tags -->
    <br />
    <div class="tags custom-tags">
      <span
        class="tag is-light"
        v-for="(tagName, index) in skillTags"
        v-bind:key="index"
      >
        {{ tagName }}
      </span>
    </div>

    <!-- Services -->
    <section class="section" id="services">
      <div class="section-heading section-text">
        <h3 class="title is-2">Services</h3>
        <h4 class="subtitle is-5">提供する価値</h4>
      </div>
      <div class="container">
        <div class="columns">
          <div class="column">
            <div class="box">
              <div class="content">
                <h4 class="title is-5">Front End Web Development</h4>
                Develop Front End using latest standards with HTML5/CSS3 with
                added funtionality using JavaScript and Vue.js.
              </div>
            </div>
          </div>
          <div class="column">
            <div class="box">
              <div class="content">
                <h4 class="title is-5">Back End Web Development</h4>
                Develop Back End application/service using Node.js or ASP .NET
                and SQL server or Mongo DB databases.
              </div>
            </div>
          </div>
        </div>

        <div class="columns">
          <div class="column">
            <div class="box">
              <div class="content">
                <h4 class="title is-5">Front End Web Development</h4>
                Develop Front End using latest standards with HTML5/CSS3 with
                added funtionality using JavaScript and Vue.js.
              </div>
            </div>
          </div>
          <div class="column">
            <div class="box">
              <div class="content">
                <h4 class="title is-5">Back End Web Development</h4>
                Develop Back End application/service using Node.js or ASP .NET
                and SQL server or Mongo DB databases.
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Resume -->
    <!-- <section class="section" id="resume">
      <div class="section-heading section-text">
        <h3 class="title is-2">Resume</h3>
        <h4 class="subtitle is-5">More about my past</h4>
        <a href="#" class="button is-link is-medium">
          <span class="icon">
            <i class="fas fa-file-alt"></i>
          </span>
          <span>Download My Resume</span>
        </a>
      </div>
    </section> -->

    <!-- Portfolio -->
    <section class="section" id="portfolio">
      <div class="container">
        <div class="section-heading section-text">
          <h3 class="title is-2">Portfolio</h3>
          <h4 class="subtitle is-5">直近作ったものたち</h4>
        </div>
        <br />

        <div class="container portfolio-container">
          <div class="columns">
            <div class="column is-4">
              <!-- admin -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Admin <small>(Light)</small></span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-danger">WIP</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/admin.png"
                      alt="Admin template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/admin.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/admin.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- cards -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Cards</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/cards.png"
                      alt="Cards template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/cards.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/cards.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- forum -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Forum</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/forum.png"
                      alt="Hero template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/forum.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/forum.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- insta album -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>InstaAlbum</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/instaalbum.png"
                      alt="Landing template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/instaAlbum.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/instaAlbum.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- landing -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Landing</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/landing.png"
                      alt="Landing template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/landing.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/landing.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
            </div>
            <div class="column is-4">
              <!-- band -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Band</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/band.png"
                      alt="Band template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/band.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/band.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- cheatsheet -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Cheatsheet</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://dummyimage.com/555x255/000/fff"
                      alt="Cheatsheet template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/cheatsheet.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/cheatsheet.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- hero -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Hero</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/hero.png"
                      alt="Hero template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/hero.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/hero.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!--kanban -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Kanban</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/kanban.png"
                      alt="Kanban template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/kanban.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/kanban.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- login -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Login</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/login.png"
                      alt="Login template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/login.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/login.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
            </div>
            <div class="column is-4">
              <!-- blog -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Blog</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-danger">WIP</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/blog.png"
                      alt="Blog template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/blog.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/blog.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!-- cover -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Cover</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/cover.png"
                      alt="Cover template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/cover.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/cover.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!--inbox -->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Inbox</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">Mobile</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/inbox.png"
                      alt="Inbox template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/inbox.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/inbox.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!--kanban with functional search-->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Kanban with Search box</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://bulmatemplates.github.io/bulma-templates/images/kanban2.png"
                      alt="Kanban template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a
                    href="templates/kanban[search].html"
                    class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/kanban[search].html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
              <!--tabs-->
              <div class="card">
                <header class="card-header">
                  <p class="card-header-title">
                    <span>Modal Cards</span>
                    <span class="is-pulled-right">
                      <a
                        href="https://github.com/jgthms/bulma/releases/tag/0.7.2"
                      >
                        <span class="tag is-default">v0.7.2</span>
                      </a>
                      <span class="tag is-default">Desktop</span>
                      <span class="tag is-default">?</span>
                    </span>
                  </p>
                </header>
                <div class="card-content">
                  <figure class="image">
                    <img
                      src="https://dummyimage.com/555x255/000/fff"
                      alt="modal-cards template screenshot"
                    />
                  </figure>
                </div>
                <footer class="card-footer">
                  <a href="templates/modal-cards.html" class="card-footer-item"
                    >Preview</a
                  >
                  <a
                    href="https://github.com/BulmaTemplates/bulma-templates/blob/master/templates/modal-cards.html"
                    class="card-footer-item"
                    >Source Code</a
                  >
                </footer>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Achievement Level -->
    <section class="section">
      <nav class="level">
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Tweets</p>
            <p class="title">3,456</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Following</p>
            <p class="title">123</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Followers</p>
            <p class="title">456K</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Likes</p>
            <p class="title">789</p>
          </div>
        </div>
      </nav>
    </section>

    <!-- Contact -->
    <section class="section" id="contact">
      <div class="container">
        <div class="section-heading section-text">
          <h3 class="title is-2">Contact</h3>
          <h4 class="subtitle is-5">Get in touch</h4>
        </div>
        <br />

        <div class="columns">
          <div class="column is-6 is-offset-3">
            <div class="box">
              <div class="field">
                <label class="label">Name</label>
                <div class="control">
                  <input class="input" type="text" placeholder="Text input" />
                </div>
              </div>

              <div class="field">
                <label class="label">Email</label>
                <div class="control has-icons-left">
                  <input
                    class="input"
                    type="email"
                    placeholder="Email input"
                    value=""
                  />
                  <span class="icon is-small is-left">
                    <i class="fas fa-envelope"></i>
                  </span>
                </div>
              </div>

              <div class="field">
                <label class="label">Message</label>
                <div class="control">
                  <textarea class="textarea" placeholder="Textarea"></textarea>
                </div>
              </div>

              <div class="field is-grouped has-text-centered">
                <div class="control">
                  <button class="button is-link is-large">
                    <!--                    <span class="icon">-->
                    <!--                      <i class="fas fa-envelope"></i>-->
                    <!--                    </span>-->
                    <span>Submit</span>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'
import SkillBar from '@/components/SkillBar'
export default {
  name: 'Top',
  data() {
    return {
      skills: [
        { name: 'PHP(Laravel)', value: 75 },
        { name: 'JavaScript(vue.js)', value: 30 },
        { name: 'HTML5/CSS3', value: 30 },
        { name: 'Dart(Flutter)', value: 40 },
        { name: 'Go', value: 20 },
        { name: 'Database(MySQL)', value: 45 }
      ],
      skillTags: [
        'Node.js',
        'VueJS',
        'JavaScript',
        'HTML5',
        'CSS3',
        'Bulma',
        'Bootstrap',
        'PHP',
        'Laravel',
        'MySQL',
        'AWS',
        'Go',
        'Flutter',
        'PHPUnit',
        'Git',
        'RESTful API',
        'JetBrains',
        'Nginx',
        'firebase',
        'serverless'
      ]
    }
  },
  components: {
    Header,
    Footer,
    SkillBar
  }
}
</script>

<style scoped lang="scss">
.section-text {
  text-align: center;
}
</style>
