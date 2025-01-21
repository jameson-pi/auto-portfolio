
<script>
    import data from "$lib/info.json";
    import Header from "$lib/header.svelte";
    import Parallax from "$lib/paralax.svelte";
    import Paralax from "$lib/paralax.svelte";
    let name = data.name;
    let title = data.title;
    let description = data.summary;
    let jobs = data.experience;
    let projects = data.projects;
    $: contacts = Object.values(data.contact);
</script>

<style>
    body {
  font-family: Roboto, sans-serif;
  margin: 0;
  padding: 0;
    background: #f8f9fa;
  
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ddd;
  backdrop-filter: blur(20px);
}

.title {
  text-align: left;
  margin-bottom: 40px;
}

h1 {
  color: #007bff;
}

h2 {
  color: #6c757d;
}

.projects, .jobs {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 20px;
  padding: 20px;
  box-shadow: 20px;
}

.project, .job, .contacts, .skills, .title{
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.headshot {
    margin-left: auto;
    margin-right: 10px;
    float: right;
}
.project a {
  text-decoration: none;
  color: #007bff;
}

.project a:hover {
  color: #0056b3;
}
</style>

<div class="container">
    <Paralax />
    <Header />
    <div class="jobs">
        <div class="title">
            <h1>{name}</h1>
            <h2>{title}</h2>
            <p>{description}</p>
        </div>
        <div class="title headshot">
            <img src="/headshot.png"/>
        </div>
    </div>
        <div class="skills">
            <h2>Skills</h2>
            <ul>
                {#each data.skills as skill}
                    <li>{skill}</li>
                {/each}
            </ul>
        </div>
    <h2>Experience<br></h2>
    <div class="jobs">
        
        {#each jobs as job}
            <div class="job">
                <div class="job-header">
                    <h3>{job.position}</h3>
                    <h4>{job.company}</h4>
                </div>
                <p>{job.startDate}-{job.endDate}</p>
            </div>
        {/each}
    </div>
    <h2>Projects</h2>
    <div class="projects">

        {#each projects as project}
            <div class="project">
                <h3>{project.name}</h3>
                <p>{project.description}</p>
                <a href={project.link} target="_blank">View Project</a>
                <h4>Technologies</h4>
                <ul>
                    {#each project.technologies as tech}
                        <li><p>{tech}</p></li>
                    {/each}
                </ul>
            </div>
        {/each}
    </div>
    <div class="contacts">
        <h2>Contact</h2>
            {#each Object.entries(data.contact) as [title, contact]}
                <p><strong>{title}:</strong> {contact}</p>
            {/each}
    </div>

</div>