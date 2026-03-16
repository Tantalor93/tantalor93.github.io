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
      Hello, my name is <strong>Ondřej Benkovský</strong>. I am a systems-focused software engineer with over <strong>10 years of experience</strong> in building robust backend solutions ranging from various web application to low-level network services like DNS servers.
    </p>

    <p>
      I specialize in building scalable backend solutions with a lot of experience in distributed and performance-sensitive applications for tackling real-world challenges efficiently. My go-to programming languages are <strong>Java</strong> and <strong>GoLang</strong>, and I have extensive experience designing and running applications on cloud infrastructure and Kubernetes clusters.
    </p>

    <p>
      Beyond my professional roles, I am an active contributor to the open-source community as a <strong>maintainer for the CNCF CoreDNS project</strong> and the creator of <strong>DNSpyre</strong>, a CLI tool for DNS load testing.
    </p>

    <p>
      Outside of coding, you'll often find me immersed in a good <strong>fantasy book series</strong> (big fan of Brandon Sanderson or Steven Erikson), playing games on my computer or PlayStation, or enjoying nature through long walks.
    </p>
  </div>

</div>

<style>
  .about-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    margin-top: 1rem;
  }

  .about-profile-img img {
    width: 180px;
    height: 180px;
    border-radius: 12px;
    object-fit: cover;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    border: 1px solid #eee;
    transition: transform 0.2s ease;
  }

  .about-profile-img img:hover {
    transform: translateY(-5px);
  }

  .about-text {
    flex: 1;
    line-height: 1.6;
    font-size: 1.05rem;
  }

  @media (min-width: 768px) {
    .about-container {
      flex-direction: row;
      align-items: flex-start;
      gap: 3rem;
    }
    
    .about-profile-img img {
      width: 240px;
      height: 240px;
    }
    
    .about-text {
      text-align: left;
    }
  }

  @media (max-width: 767px) {
    .about-container {
      text-align: center;
    }
    .about-profile-img {
      margin-bottom: 0.5rem;
    }
  }
</style>
