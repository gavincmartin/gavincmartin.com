+++
# Experience widget.
widget = "experience"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 40  # Order that this section will appear.

title = "Experience"
subtitle = ""

# Date format for experience
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format = "Jan 2006"

# Experiences.
#   Add/remove as many `[[experience]]` blocks below as you like.
#   Required fields are `title`, `company`, and `date_start`.
#   Leave `date_end` empty if it's your current employer.
#   Begin/end multi-line descriptions with 3 quotes `"""`.
[[experience]]
  title = "Senior Software Development Engineer"
  company = "Amazon - Project Kuiper"
  company_url = "https://www.amazon.com/"
  location = "Redmond, Washington"
  date_start = "2024-04-01"
  date_end = ""
  description = """
  In my current role, I work on the Mission Operations team for Project Kuiper. I build constellation operations software for a variety of planning, execution, and automation use cases so that we can successfully operate our satellites as we continue to scale the constellation.
  """


[[experience]]
  title = "Software Development Engineer II"
  company = "Amazon - Project Kuiper"
  company_url = "https://www.amazon.com/"
  location = "Redmond, Washington"
  date_start = "2022-05-01"
  date_end = "2024-04-01"
  description = """
  In my role as an SDEII on the Mission Operations team, I helped our team drive operational readiness for our Protoflight satellite launch in October 2023. 

  As a precursor to on-orbit operations, I was heavily involved in hardware-in-the-loop testing of our flatsats and actual satellites on the ground. Our team developed test frameworks for running everything from lower-level functional tests up to high-level system integration tests to exercise key concepts of operations. We also built out automated reporting pipelines and dashboards using AWS services to drive progress in cross-program test campaigns.

  In addition to test work, we created a mission operations platform that empowered flight operators to author and execute Jupyter notebooks as ops procedures hosted on AWS SageMaker, and we built out a rich Python library to support ops use cases.

  I was lucky enough to serve as the flight controller for one of our two Protoflight satellites on launch day. You can briefly catch me in the [Project Kuiper Protoflight Mission: Launch Day Highlights](https://www.youtube.com/watch?v=4CScMjPE744) video.

  After the Protoflight launch, I worked on operations software to support scaling the constellation from 2 to 3000+ satellites, and I continued this work in my role as a Senior SDE.
  """

[[experience]]
  title = "Software Systems Engineer"
  company = "NASA Jet Propulsion Laboratory"
  company_url = "https://www.jpl.nasa.gov/"
  location = "Pasadena, California"
  date_start = "2020-01-13"
  date_end = "2022-04-30"
  description = """
  Once I joined JPL full-time, I was given the opportunity to spin up and lead a team of
  4 engineers in developing activity planning software for the Europa Clipper mission. This task built upon my prior experiences in multi-mission ground software development and Europa Mission Planning.

  Over the next 2.5 years, we scaled the team from 4 to 10 engineers.

  We designed next-generation planning systems to support distributed spacecraft operations at institutions across the U.S. We built software to model highly-complex systems, check system constraints, intelligently schedule ground & spacecraft behaviors, and empower operators to make effective decisions which preserve spacecraft safety while maximizing scientific output.
  """

[[experience]]
  title = "Software Systems Engineering Intern"
  company = "Raytheon / NASA Jet Propulsion Laboratory"
  company_url = "https://www.jpl.nasa.gov/"
  location = "Remote / Pasadena, California"
  date_start = "2019-04-01"
  date_end = "2019-12-01"
  description = """
  I spent much of 2019 working at JPL as an intern--remotely during my spring and fall semesters as a Raytheon contractor to JPL and full-time (as an intern) in Pasadena over the summer.

  I served as a representative for the Europa Clipper mission on a multi-mission software development team and collaborated on a Java framework for spacecraft activity planning and mission simulation. Specifically, I focused on designing the spacecraft modeling components of the framework and in developing a discrete event simulation engine to drive simulations.
  """

[[experience]]
  title = "Mission Planning Intern"
  company = "NASA Jet Propulsion Laboratory"
  company_url = "https://www.jpl.nasa.gov/"
  location = "Pasadena, California"
  date_start = "2018-05-01"
  date_end = "2018-08-01"
  description = """
  I interned with the Mission Planning team on NASA's flagship Europa Clipper
  mission and spent my summer automating modeling, simulation, and analysis processes in support of trajectory evaluation and science planning use cases.
  """

[[experience]]
  title = "Seeker Vision Project Manager"
  company = "Texas Spacecraft Laboratory"
  company_url = "http://sites.utexas.edu/tsl/"
  location = "Austin, Texas"
  date_start = "2017-10-01"
  date_end = "2018-05-01"
  description = """
  I served as the Project Manager for the Seeker Vision project--an effort to
  endow NASA JSC's Seeker-1 CubeSat with "intelligent" vision capabilities.

  Our team adapted state-of-the-art convolutional neural network (CNN) architectures
  to the space environment and trained them to detect, recognize, and provide
  relative bearing estimates for a target spacecraft (Cygnus) while in orbit.
  We used the TensorFlow Object Detection API and OpenCV to write flight software
  that was resilient to varied vehicle orientations, lighting conditions, and backdrops
  and was capable of running on a low-powered CubeSat flight computer.

  Our computer vision system was integrated onto the flight unit and was actually used for proximity operations in space. **Seeker-1 launched on Cygnus NG-11 in April 2019 and was deployed after a Cygnus re-supply in September 2019**.
  """

[[experience]]
  title = "ARMADILLO Mission Manager"
  company = "Texas Spacecraft Laboratory"
  company_url = "http://sites.utexas.edu/tsl/"
  location = "Austin, Texas"
  date_start = "2017-03-01"
  date_end = "2017-11-01"
  description = """
  I helped revive UT-Austin's Texas Spacecraft Laboratory after over a year of dormancy,
  and I served as its first student leader. In this role, I scaled the student-driven lab from 5 to over 50 members, overcoming training, communication, and management challenges along the way.
  
  I also managed the lab's ARMADILLO mission: a CubeSat funded by the Air Force Research Laboratory for measurement of sub-millimeter space debris. We built the operations infrastructure necessary to support the spacecraft once in orbit, passed all of our AFRL reviews, and **ARMADILLO successfully launched on a SpaceX Falcon Heavy in 2019 (STP-2)**.
  """

[[experience]]
  title = "Software Engineering Intern"
  company = "GE Aviation"
  company_url = "https://www.geaviation.com/"
  location = "San Marcos, Texas"
  date_start = "2016-05-01"
  date_end = "2016-08-01"
  description = """
  """

[[experience]]
  title = "Research Intern, International Economics Program"
  company = "James A. Baker III Institute for Public Policy | Rice University"
  company_url = "https://www.bakerinstitute.org/"
  location = "Houston, Texas"
  date_start = "2015-06-01"
  date_end = "2015-08-01"
  description = """
  """

[[experience]]
  title = "Computer Science Tutor"
  company = "Houston Independent School District"
  company_url = "https://www.houstonisd.org/"
  location = "Houston, Texas"
  date_start = "2015-02-01"
  date_end = "2015-05-01"
  description = """
  """

[[experience]]
  title = "Research Assistant"
  company = "Baylor College of Medicine"
  company_url = "https://www.bcm.edu/"
  location = "Houston, Texas"
  date_start = "2014-06-01"
  date_end = "2014-08-01"
  description = """
  """

+++
