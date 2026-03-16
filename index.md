---
layout: page
title: About Me
---

<div class="about-container">

  <div class="about-profile-img">
    <a href="{{ site.baseurl }}/assets/images/profile.jpeg" target="_blank">
      <img src="{{ site.baseurl }}/assets/images/profile.jpeg" alt="Ondřej Benkovský">
    </a>
  </div>

  <div class="about-text"> 
    <p>
      Hello, my name is <strong>Ondřej Benkovský</strong>. I am a systems-focused software engineer with over <strong>10 years of experience</strong> in building robust backend solutions. My work ranges from high-level web applications to low-level network services like DNS servers.
    </p>

    <p>
      I specialize in building scalable, distributed, and performance-sensitive applications. I am particularly passionate about <strong>GoLang</strong> and <strong>Java</strong>, and I have extensive experience in designing and running applications on cloud infrastructure and Kubernetes clusters.
    </p>

    <p>
      Beyond my professional roles, I am an active contributor to the open-source community as a <strong>maintainer for the CNCF CoreDNS project</strong>, which is a vital part of the Kubernetes ecosystem. I also created <strong>DNSpyre</strong>, an open-source tool for DNS load testing.
    </p>

    <p>
      Outside of coding, you'll often find me immersed in a good <strong>fantasy book series</strong> (big fan of Brandon Sanderson or Steven Erikson), playing games on my PC or PlayStation, or enjoying nature through long walks.
    </p>
  </div>

</div>

<style>
  .about-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2.5rem;
    margin-top: 2rem;
  }

  .about-profile-img img {
    width: 220px;
    height: 220px;
    border-radius: 50%;
    object-fit: cover;
    box-shadow: 0 10px 25px rgba(0,0,0,0.1);
    transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    border: 3px solid #f0f0f0;
  }

  .about-profile-img img:hover {
    transform: scale(1.05);
  }

  .about-text {
    flex: 1;
    line-height: 1.7;
  }

  .about-text p {
    margin-bottom: 1.2rem;
  }

  @media (min-width: 768px) {
    .about-container {
      flex-direction: row;
      align-items: flex-start;
      text-align: left;
    }
    
    .about-profile-img {
      flex-shrink: 0;
      position: sticky;
      top: 20px;
    }
  }

  @media (max-width: 767px) {
    .about-container {
      text-align: center;
    }
  }
</style>
