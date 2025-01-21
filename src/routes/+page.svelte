
<script>
    import data from "$lib/info.json";
    import header from "$lib/header.svelte";
    let name = data.name;
    let title = data.title;
    let description = data.summary;
    let jobs = data.experience;
    let projects = data.projects;
</script>

<style>
    body {
  font-family: Roboto, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #fff;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ddd;
}

.title {
  text-align: center;
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
}

.project, .job {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
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

    <div class="title">
        <h1>{name}</h1>
        <h2>{title}</h2>
        <p>{description}</p>
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
            </div>
        {/each}
    </div>
</div>