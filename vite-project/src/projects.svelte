<script>
  import { onMount } from 'svelte';
  import CodePanel from './codePannel.svelte';
  export let navigate = (p) => (location.pathname = p);

  //HD imports
  import thumb1 from './assets/hartydarty/IMG_2250.jpeg';
  import img1a from './assets/hartydarty/DSC06724.jpg';
  import img1b from './assets/hartydarty/DSC06780.jpg';
  import img1c from './assets/hartydarty/DSC06782.jpg';
  import img1d from './assets/hartydarty/DSC06786.jpg';
  import img1f from './assets/hartydarty/DSC06795.jpg';
  import img1g from './assets/hartydarty/DSC06829.jpg';
  import img1h from './assets/hartydarty/IMG_2183.jpeg';
  import img1j from './assets/hartydarty/IMG_2528.jpg';


  //L2 Imports
  import img2a from './assets/l2/cad.png';
  import img2b from './assets/l2/fails.jpg';
  import img2c from './assets/l2/IMG_1875.jpeg';
  import img2d from './assets/l2/openrocket.png';
  import img2e from './assets/l2/IMG_1789.jpeg';
  import img2f from './assets/l2/DSCF1001.jpg';
  import img2g from './assets/l2/IMG_3540.jpeg';
  import img2h from './assets/l2/IMG_3542.jpeg';
  import img2i from './assets/l2/IMG_3546.jpeg';
  import img2j from './assets/l2/IMG_4355.JPG';

  //Website imports
  import thumb3 from './assets/r.jpeg';
  import img3a from './assets/IMG_2259.jpeg';
  import img3b from './assets/IMG_3456.jpeg';

  //UI dev imports
  import thumb4 from './assets/ui/IMG_0563.jpeg';
  import img4a from './assets/ui/cal.png';
  import img4b from './assets/ui/chopin.png';
  import img4c from './assets/ui/dash.png';
  import img4d from './assets/ui/finances.png';
  import img4e from './assets/ui/match.png';
  import img4f from './assets/ui/quiz.png';
  import img4g from './assets/ui/schedule.png';
  import img4h from './assets/ui/wardrobe.png';
  import img4i from './assets/ui/article.png';
  import img4j from './assets/ui/closegap.png';

  //double or nothing imports
  import thumb5 from './assets/doubleOrNothing/IMG_4894.jpg';
  import img5a from './assets/doubleOrNothing/20260411_205010000_iOS 1.jpg';
  import img5b from './assets/doubleOrNothing/1000003021.jpg';
  import img5c from './assets/doubleOrNothing/DSC07361.jpg';
  import img5d from './assets/doubleOrNothing/DSC07417.jpg';
  import img5e from './assets/doubleOrNothing/DSC07468.jpg';
  import img5f from './assets/doubleOrNothing/DSC07490.jpg';
  import img5g from './assets/doubleOrNothing/IMG_1667.jpeg';
  import img5h from './assets/doubleOrNothing/IMG_1726.jpg';
  import img5i from './assets/doubleOrNothing/PXL_20260411_192521324.jpg';

  //TOBI imports
  import thumb6 from './assets/TOBI/pcbThumb.png';
  import img6a from './assets/TOBI/figma.png';
  import img6b from './assets/TOBI/full_ebay.png';
  import img6c from './assets/TOBI/IMG_4334.PNG';
  import img6d from './assets/TOBI/IMG_4335.PNG';
  import img6e from './assets/TOBI/KicadFront.png';
  import img6f from './assets/TOBI/lipo_ebay.png';
  import img6g from './assets/TOBI/openRocket.png';
  import img6h from './assets/TOBI/pcb_ebay.png';
  import img6i from './assets/TOBI/TOBI_schematics.pdf';


  let projects = [
    {
      id: 6,
      title: "TOBI - Custom Flight Computer", 
      role: "Embedded Systems & Full-Stack Development",
      date: "May 2026 - Present",
      tags: ["Rocketry", "Avionics","Hardware", "Aerospace", "Embedded Systems", "C++", "PCB"],
      tech: ["PlatformIO", "C++", "KiCAD, Embedding systems, Microcontrollers", "OpenRocket"],
      preview: "University of Cincinnati's first two stage rocket Custom Avionics Bay",
      content: [
        "Learning from Harty Darty and Double or Nothing, as a method of learning more about avionics and embedded systems, I created TOBI which allowed me to work on every aspect of the project from scratch and entirely on my own. Although I did use similar components optimized for the immense G forces when the rocket is launch, all designs, PCBs, and code was entirely created from scratch by myself. TOBI, Telemetary Orientation and Barometric Instrument (Flight Computer), is also an extension of the Japanese word 飛びる(tobiru) meaning to soar. This is ultimately the backbone for further projects with UCRC and our fall project in Kanas as well as my capstone project to later compete in IREC in Texas, 2027.",
        "Components are entirely similar, using the Seeed ESP32-S3 as a microcontroller, MS561101 for the barometer, and the Adafruit LSM6DSO32. The electronics bay and PCB are optimised for a 2 inch diameter with the LiPo batteries wired from under the PCB. There is additional space as seen in the overal e-bay render where you could test a COTS system to compare and ensure parachute deployment and or additional payload for testing. All code was developed in C++ and HTML using PlatformIO. ",
        "My goals this semester overall was: learn more about embedded systems, work on multi-threaded code, and create a good base project for further more specific version of TOBI. ",
        "",
      ],
      bullets: [
        "Implemented further multithreading",
        "Completed PCB designs from scratch to production",
        "Continued work on sensor integration in real time",
        "Developed a new real-time server with the ESP to retrieve CSV & live data",
      ],
      links: [
        { label: "Current GitHub Repo", href: "https://github.com/raniahaas/TOBI", external: true },
      ], 
      thumb: [thumb6],
      images: [img6a, img6b, img6c, img6d, img6e, img6f, img6g, img6h, thumb6, img6i],
      captions: [
        "Full Figma sketch of front end UI desing for the active reading and CSV download.",
        "Full 3D printed ebay design in Fusion360.",
        "ESP32S3 successfully creating local host and connection with user.",
        "Front end UI of the start up screen for user, recording live data. ",
        "Top model of the PCB in KiCAD.",
        "Closer view of the middle part of the ebay, section created for two LiPo batteries.",
        "OpenRocket model of the Wildman Darkstart Jr, the rocket to be used to test the flight computer. PCB is inherently modeled for the ebay with a diameter of 2” rather than the typical 38 mm min diameter. ",
        "Another view focusing more on the PCB sitting at the top of the ebay, location was picked to easily allow quick access to arm or disarm the device.",
        "PCB final design render from JLC PCB."
      ]
    },
    {
      id: 1,
      title: "Two Stage Avionics Flight System", 
      role: "Avionics Team Member - Customs Developer",
      date: "January 2026 - April 2026",
      tags: ["Rocketry", "Avionics","Hardware", "Aerospace", "Embedded Systems", "C++"],
      tech: ["PlatformIO", "C++", "KiCAD, Embedding systems, Microcontrollers",],
      preview: "University of Cincinnati's first two stage rocket Custom Avionics Bay",
      content: [
        "Following up on the Fall semester's Harty Darty, Double or Nothing was born as the next natural progression for the club, becoming the first two stage rocket in both UC history as wel as the club's. Goals for the project can be simplifed into three categories: generalised, structures, and avionics. Generally, the overall goal was to stay within our given flight waiver at WSR of 10,000ft but no less than 8,000ft. Additionally, it was a heavy priority to have both stages recoverable within a mile raidus of launch. This is a good rule of thumb to begin with, but with the inner stage of Harty Darty not being recoverable for about a month, it was an even higher priority item this time. For structures, the goals was to efficienty optimize a two stage rocket, continue to build a Mach 1 capable rocket, and improve simulation techniques. For avionics, the goals encompassed ignition of a second stage as well as recovery in terms of custom components.",
        "Similar to Harty Darty, Avionics is once again running off of a custom electronics bay as well as off the shelf compoents, both being near identical to the previous semester's project. One of the larger changes we added this semester was PCB design to decrease latency as well as set the club up with the skills accredidted to a space launch later down the line. On the PCB, we still used our ESP32-S3 microcontroller, MS5611 barometer, and LSM6DSO32 IMU. With the nature of the project, we used C++ and PlatformIO to be able to integrate and flash the information as an alternative to the ArudinoIDE. The goal was to maximise the flash memory, using about half of the volatile memory for logging and determining event sequences. Primarily, the largest being from high speed data coming from the IMU. It is important to note here that we are using customs as a development feature to later connect to pyrotechniques, given myself and the few others working on customs completely dependent code was not in the cards this semester.",
        "Working off of the code from the previous semester, I had set out a few goals for moving forward with the project: clean up the code and create more intuitive functions, create better logging techniques for data retrival, add more staging events and faux events to replace what would be pyrotechniques. Before any of these goals could be addressed--there was a larger issue at hand. After retriving information from last semester and with simulations ran on the custom code, the setup of the microcontroller wihtout any multi-threading made it impossible to both log information from the barometer or accelerometer as well as have event logging. Often when testing, all of the values would be recorded but when the computer determined it 'landed' the functions would then go through and record the event sequence with inacurrate data points and times. To comabt this, we used freeROTS to create some multithreaded code to have one core constantly log information and the other detect and determine event sequences. This became the hardest part of our integration, which often required re-writing the entire logic for all of our functions to work with the multithreading techniques.",
        "Not knowing the scale of multithreading and the overall complexity ended up being one of the greatest weak points of the code this semester, although the logic was there actual implementation and testing became quite difficult once we realised the scale. Before launch day, the multi-threading was sucessfully in place but we were still lacking in many features, notably only truly flying with apogee detection, launch and staging detection, and landing which was less than we had originall bargined for. However, the large learning curve that came with multi-threading ended up being quite the large step in the customs code development, setting a the club off on a good base for the next project. Considering my goals, I was able to help contribute to cleaning up the code as well as teaching more members the innerworking of the code, but still left many quetsions unaswered for the next project.",
        "One of the most important things I can take away from this project this semester is truly planning around the unknown. Without knowing the scale of issues that came with multithreading and only two programmers working on this difficult aspect, priorites for the final demostration become a lot larger. Truly marking out in the beginning what is critical and must be done no matter the issues we run into is something I plan to use going forward with development of my own custom flight computer. Additionally, how important it is to be able to write clear and consice code for many to understand when I am long gone. I would often create headers at the top of files with dates, initials, and modifications made which helps along side git to determine who is working on which functions, why, and what modifications were changed from previous versions. I found this truly critical when integrating others code into our multi-threaded versions. On a similar note as well, how important it is to explain concepts to new coders. Being the only computer science major within the project and working on the code, the exposure of higher level programming concepts was a large gap between myself and the other aerospace majors. Creating code in a way that is very digestable and simple to understand in a coding perspective and more in a physics perspective is something I plan to focus on when writing more code.",
        "This project truly was such a fun endevour, but also pushed me outside of my comfort zone working more hands on with the development and the embedded system aspect of the project. For our method of lighting the second stage being very experimental, seeing the whole project work sucessfully is a feeling truly unmatched. For our final stats of the first stage: Apogee of 3,539.71ft with a total time of 14.4 seconds, max velocityof 612ft/s (0.55 mach), motor burnout of 1.3 seconds at a tilt of 11.2º, main parachute deployment at 689 feet decescending at 37.6 ft/s. Overall second stage stats: apogee of 10,116.75 ft encapsulating 25.4s, max velocity of 1046.0ft/s (0.93 mach), 2.2 second delay between stages, 5.27 s second motor burn out at a tilt of 14.2º, drogue descent at 58ft/s. ",
        "More information regarding indepth images, sketches, mathematics, and structures can be found attached to the GitHub repository. Huge shout outs to our leads this semester for truly creating and cementing their names in history, Project Manager Jesse Dominguez, Structures lead Caleb Leech, and Avionics Lead Loring Teuteberg"
      ],
      bullets: [
        "Developed new multithreading techniques and usage",
        "Used Euclidean norm for calcuating apogee",
        "Created test cases, systems for data management, and instructions for conceptual functions",
        "Continued work on sensor integration in real time",
        "Developed a new real-time server with the ESP to retrieve CSV data",
        "Learned more critical functions regarding model rocketry and integration of a custom flight computer with pyrotehcniques"
      ],
      links: [
        { label: "Current GitHub Repo", href: "https://github.com/raniahaas/DoubleOrNothing", external: true },
      ], 
      thumb: [thumb5],
      images: [img5a, img5b, img5c, img5d, img5e, img5f, img5g, img5h, thumb5, img5i],
      captions: [
        "Full Double or Nothing team, for the spring semester, launched on April 11th, 2026.",
        "Double or Nothing sitting on the pad, ready for flight!",
        "Testing simulations and continuity on the Blue Raven and Blue Jay altimeter.",
        "Avionics Lead, Loring Teuteberg, preparing the electronics bay.",
        "Loring preparing black powder pellets to ignite the second stage motor.",
        "Team Lead, Jesse Dominguez, and Loring creating the second stage motor, a H-130.",
        "Posing with the rocket post flight!!",
        "Congrats and high fives all around for making UC history! Within the Rocketry Club and campus, first Two-Stage rocket launched!",
        "Similes all around for a sucessfully recovered second stage!",
        "Final preparations before heading to the launch pad with sucessfully created motors."
      ]
    },
  
  {
      id: 2,
      title: "Boosted Dart Avionics Flight System",
      role: "Avionics Team Member - Customs Developer",
      date: "Sept 2025 – Dec 2025",
      tags: ["Aerospace", "Embedded Systems", "C++", "Avionics", "Rocketry"],
      tech: ["C++", "PlatformIO", "Git", "Microcontrollers"],
      preview: "Avionics development for the Univeristy of Cincinnati's Rocketry Club's Boosted Dart",
      content: [
        "Developed along side colleagues Loring Teuteberg and Jesse Dominguez (Avionics Lead) to create custom code for the avionics bay utilising PlatformIO in Visual Studio Code using C++.",
        "Main responsibilities included designing the control architecture, implementing sensor filtering and logging, and developing clean code for reusability",
        "Components included the Adafruit LSM6DSO32 IMU for gyroscope data and as an accelerometer. This was then recorded in G's across all axes and angular velocity in degrees per second, to allow for the analysis of thrust, stability, and stage changes. MS5611 Barometer was used to temperature and pressure. From pressure readings, we could then calculate altitude both to sea level and to the launch site in Dayton, pinpointing apogee and descent. The ESP32 Microcontroller acted as the whole brain of the operation, running flight detection logic, managing data storage, and hosting a local server we could manage for continuity.",
        "Harty Darty was a large group effort by UCRO to create a boosted dart with Mach 1 capabilities. The goals of the avionics team was to create a fully custom avionics as well as an additional fall-back bay using the Blue Raven developed by Featherweight Altimiters. Harty Darty had a semi-sucessful launch on November 23nd with a delayed separation stage (it is important to know this is a boosted dart, so the second stage did not contain a motor and was purily thrusted by the intial thrust and drag separation). ",
        "Being the second avionics project I've had the opportunity to work on, it was very rewarding to see the final project yet very difficult encountering unknown waters. Majority of my projects have been local apps and website so encorperating hardware was pretty much entierly new to me as well as understanding fundamentals of electroncis and enacted forces. I have learned a lot more about hardware and software development incoorperation, CAD, wiring, working with a team for the greater good."
      ],
      bullets: [
        "Created a localhost through the Seeeed to allow the retrival of flight-logged data in a txt file",
        "Integrated IMU and barometer data with Kalman filtering",
        "Helped develop check tests to ensure continuity",
        "Worked on senor integration, learning how to configure and read from the barometer and IMU",
        "Learned how to work on real-time connectivity with the localsever on the ESP",
        "Applied physics concepts learned in the classroom consisting of converting raw sensor data into g‑forces, angular velocity, and altitude using barometric formulas"
      ],
      links: [
        { label: "GitHub repo", href: "https://github.com/raniahaas/HardyDarty", external: true },
        { label: "YouTube", href: "https://www.youtube.com/watch?v=EhZOaHPUpec", external: true}
      ],
      thumb: thumb1,
      images: [ img1g, img1b, thumb1, img1c, img1d, img1f, img1h, img1a, img1j],
      captions: [
        "The entire Hardy Darty Team posing with the boosted dart before launch on Novemeber 23rd, 2025.",
        "Avionics Lead, Jesse Dominguez, and Avionics Member, Loring Teuteberg, preparing the electronics bay for flight.",
        "TL(D)R!",
        "Booster stage after motor assembly.",
        "Loring and Jesse setting the Avionics Bay into the dart.",
        "Adding the threaded inserts to lock in the Avionics Bay.",
        "Initial breadboard testing of the avionics bay.",
        "Loring testing for continuity and flight control for the Blue Raven.",
        "Harty Darty taking launch!"
      ]
    },

    {
      id: 3,
      title: "Level 2 Certification Rocket", 
      role: "Avionics and Structures",
      date: "Sept 2025 - Present",
      tags: ["Rocketry", "Avionics","Hardware"],
      tech: ["Fusion360", "Open Rocket"],
      preview: "Creating my Level 2 certification rockets",
      content: [
        "Under mentorship of Landry Danielson, Level 2 Tripoli and UCRO President, I set a goal to gain my Level 2 certification to gain a deeper knowledge of high powered rocketry as well as avionics development and aerospace community alongside taking the Level 2 test for certification primarily through a two-stage cardboard rocket.",
        "Using a 4 in diamater on a J-800 motor, the Open Rocket simulation is predicted for the rocket to achieve an apogee of 4,900ft with a max velocity of over 1,000 ft/s. The entire rocket except for the fins are made of re-enforced cardboard with a 3D printed custom avionics bay.",
        "Intial launch occured on May 2nd--and has had many trials and tribulations along the way! After achieving my Jr Level 1 (now just Level 1) back in the fall of 2021, there was quite a bit I needed to re-learn about development of a new rocket with an unfamiliar matieral. Unlike previously working on our Harty Darty Rocket or Double or Nothing, my avionics bay this time was completely on my own and luckily was loaned components from the club to use. Although I have previously worked on physical impelemntation with a breadboard and understanding the fundamentals of wiring, this proved to be still a skill I want to work harder at with my lack of understanding and efficency. In addition, developing a electronics bay using Fusion 360 was entirely new and as I am sure Landry could atest, I am quite poor at. Half of the journey is learning what you don't know and this was a beautiful example of new skills that I want to improve on. ",
        "After 9 months, I was offically able to Launch my first L2 capable rocket, Kaze Tachinu, which is a node to Miyazaki Hayao film As the Wind Rises, about Jiro Horikoshi's development of the WW2 Japanese fighter-jets. During launch the rocket CATOed, due to the motor casing being incompatible with the J-800 motor I was running. It was a simple error of putting the incorrect motor casing alongside the motor. A big factor of this was there was a large gap, approximately 2 inches, between the top of the motor and the rest of the casing, which when pressurized and given room to expand, simply explodes instead of creating and directing the thrust we search for. Luckily, the top half off the rocket, including the electronics bay, was recovered in perfect condition. Truly was a great learning experience not only for myself, but the others at the launch site to see what a burned-through motor casing looked like!",
        "This was an overall great learning experience from the actual development of the rocket, but lots from actual launch day as well. I truly learned the greatest life lesson of always double-checking your materials, and creating an SOP. When it comes to rocket science, you cannot play around and truly small mistake like these can cost you no matter the scale.",
        "Moving forward, the plan is to create another L2 rocket, primarly made of carbon fiber, using the same electronics and overall setup of the carboard version. The overall consenus I have come to in regards to changing from cardboard to carbon fiber is mainly due to the reusability and future of the L2 and for further testing and development of a purley custom flight computer."
      ],
      bullets: [
        "Developing stable rockets in Open Rocket",
        "Created custom Avionics with modeling in Fusion360",
        "Using off the shelf components in a two-stage rocket",
        "Understanding the qualifications for a Level 2 capable rockets",
        "Grasping a larger understanding of better saftey protocols",
        "Understanding the importance of an SOP",
      ],
      thumb: img2h,
      images: [img2d, img2f, img2a, img2b, img2c, img2e, img2g, img2h, img2i, img2j],
      captions: [
        "OpenRocket design of the Level 2 Rocket.",
        "Using a dual-redundant system with two stratologgers on a 3D-printed custom avionics bay.",
        "CAD rendering of the custom avionics bay in Fusion360.",
        "Initial testing and finished products after 3D printing.",
        "Initial alignment of fins within the body tube.",
        "Final CAD design of the Avionics Bay.",
        "風立ちぬ or As the Wind Rises, sitting ready for launch!",
        "Launch pad pictures before flight.",
        "Unfortunate landing, with all shearpins and the upperbody tube intact.",
        "Exploded motor casing, truly a shocking feat."
      ]
    },

    {
      id: 4,
      title: "Portfolio Website",
      role: "Full Stack Developer",
      date: "Oct 2025 – Present",
      tags: ["Web Development", "Svelte", "Design"],
      tech: ["Svelte", "Tailwind", "NPM Packages", "Git Pages"],
      preview: "A comprehensive website to showcase projects, full resume, and humility of programming",
      content: [
        "This site is my personal portfolio — a space where design meets engineering. One of my greatest life-long passions outside of engineering that plays a major role in my life is my time spent in the Japanese language and wanted a place to showcase and use these skills! Developing a bilingual portfolio site to have a more indepth area to showcase and explain my current projects seemd perfect! Goal was to make an interactive website using Svelte to integrate a resume as well as characteristics of myself into one website.",
        "I focused a lot on a responsive layout, both the Japanese and English content, and a small, fast bundle. This website is more than a portfolio--it’s a living notebook of experiments, iterations, and milestones. It reflects how I approach design and development: methodical, imaginative, and always evolving! "
      ],
      bullets: [
        "Created website from scratch using Svelte and Vite",
        "Implemented a projects feed with thumbnails and focused views",
        "Built a language toggle button with persisted preference.",
        "Learned more about embedding of media: images, video, and code",
        "Truly grasping a better understanding of user-usability and creative elements",
        "Iterative refinement of testing, debugging, and polishing small details until both design and code feel seamless"
      ],
      thumb: thumb3,
      images: [img3a, img3b],
      captions: [
        "Initial	development of this website during development and testing",
        "Coding never stops!",
      ]
    },

    {
      id: 5,
      title: "User Interfaces",
      role: "Full Stack Developer",
      date: "Sept 2025 – December 2025",
      tags: ["Web Development", "Svelte", "Design"],
      tech: ["Svelte", "Tailwind", "NPM Packages", "Git Pages"],
      preview: "Projects I have developed in the Unversitys' User Interfaces Course",
      content: [
       "Over the Fall Semester of 2025, I was able to take a user interfaces course under Dr. Jillian Aurisano, looking into truly good and bad user interfaces, how they may effect the user's experience, and common mistakes. We were given four projects to develop of over the semester: a journal, a 'smart' interface, fix a bad interface, and finally create something to help solve a world problem.",
       "First, we created a journal. This was right after we did a little bit of practice in Svelte and I created Chopin Chronicle. The goal of Chopin Chronicle was to have an interactive enviornment for a user to log their current classical music obsessions. One of the best parts of this course was truly making things that I felt mattered to me. I wanted to create an enviornment where the user could log (and encourage going to) concerts and performances as well as see upcoming concerts in the area. The user is also reccomended pieces based on their entires--each day the user can make a journal entry about the performance they attended and report about the type such as Baroque or Romantic era. Since this was my first true project, there are still a lot of room for improvemnts. Currently, the music reccomendations are truly not dynamic and would also want to embedd YouTube and Spotify playlists. Instead of having one scrolling screen, I think it would be great to make multiple tabs. Truly, however it was a great start!",
       "Next, instead of a solo project we did a group project to create an interface if an object of our choice was electronic. A good example is the watch from Spy Kids, a watch with a useable user interface. Alongside Meredith Bartel, we developed a UI system as if there was an electric pannel next to a closet, creating an app similar to that of the computer used in the movie Clueless. Meredith and I created an interface where you could not only try on outfits for yourself, but as well as add new users and created a calculation based on their seasonal colors (as if you were to get your colors done) in a quick quiz. The greatest hinderance of this app (other than the fact there is no smart closet like this yet) is how to user visualises themselves in the different clothes options. Between Meredith and myself there is about a four inch height difference that clearly translates into the app. We would have to develop a better implementation of the user and sizing the clothes to fit the user better based on their height. Another feature we would have liked to add that we did not get to was shoes and other accessories. Truly no outfit is complete without them!",
       "Third, once again with Meredith we worked to fix a bad user interface. There are tons of low-budget or poorly execute apps and websites, but the best always hit close to home--hence our choice of picking the Univeristy of Cincinnati's Landing page for current and future students. I truly go a lot more indepth on the Github repo (if you would like to take a read) on the errors of this website, but one of the biggest issues is the website is very much so set up to be tailored to each student but that wasn't implemented ever. As well as lots of redundancy and missing pieces of critical information. Out of all the four projects I was able to work on this semester, this one truly turned out the best. Although there are a few missing features (only due to how the UC system is set up with linking to external pages when you need to be signed in), this project is the closest to it's polished form currently and could truly make a large difference.",
       "Finally, this was another solo project where we were tasked with picking any issue in the World, wheter it be hunger, United States legal system, anything we truly thought was flawed in our society. One thing that struck me the most that I ended up focusing on was Medicine and Faith--two things I believe my gernation is indifferent about (as in Gen Z is very atheist generation and has been on lots of medication with several diagoisis being common). I created Closing the Gap, focusing on Gen Z's conditions as well as connecting them to the Bibical view of common plaguing conditions. This was more of a love child in the articlces that I wrote over the UI implementation--but I truly wanted to be able to deliever a work that I felt was accurate information wise. It goes through herbal medicines as well as their uses to show the user there are alternatives to the hard medications given to you by Big Pharma to keep you on drugs for the rest of your life. Majority of the changes I would like to make is small things with coloring, sometimes inconsistent, as well as image sizing that sometimes gets a little funny when actually impelmented.",
       ""
      ],
      bullets: [
        "Created websites from scratch using Svelte and Vite",
        "Learned how to create a user-centred application",
        "Interation design",
        "Sketching and implementation",
        "Visual consistencies"
      ],
      links: [
        { label: "Chopin Chronicle Deployment", href: "https://chopinchronicle.netlify.app/", external: true },
        { label: "Chopin Chronicle GitHub Repo", href: "https://github.com/raniahaas/chopinChronicle", external: true},
        { label: "Mr Wardobe Deployment ", href: "https://mrwardrobecloset.netlify.app//", external: true },
        { label: "Mr Wardrobe GitHub Repo", href: "https://github.com/raniahaas/MrWardrobe", external: true},
        { label: "Bearcat Landing Re-Design Deployment", href: "https://bearcatlanding.netlify.app/", external: true },
        { label: "Bearcat Landing GitHub Repo", href: "https://github.com/raniahaas/BearcatLanding", external: true},
        { label: "Closing the Gap GitHub Repo", href: "https://github.com/raniahaas/closingTheGap", external: true},
        { label: "Closing the Gap Deployment", href: "https://closingthegap.netlify.app/articles#ocd", external: true},
        

      ], 
      thumb: thumb4,
      images: [img4b, img4a, img4c, img4d, img4e, img4f, img4h, img4g, img4i, img4j],
      captions: [
        "Landing page for Chopin Chronicle.",
        "Calendar design inside of Chopin Chronicle that takes local events around the Cincinnati Metro Area.",
        "Landing page for the redesign of the Bearcat Landing Page.",
        "Detailed finances section of the Bearcats Landing.",
        "First version of Mr. Wardrobe.",
        "Quiz for determining your colors within Mr.Wardrobe.",
        "How to use Mr. Wardrobe.",
        "Further look at course schedule and club events within the Bearcat Landing.",
        "In-depth acrticle on natural alternatives to OCD.",
        "Overall dashboard for Closing the Gap."
      ]
    },

    
    


  ];

  let expanded = null; // id of open project
  $: selected = projects.find(p => p.id === expanded) || null;

  // gallery state
  let galleryIndex = 0;

  //enlargen images when clicked in gallery
  let isZoomed = false;
  let zoomSrc = null;
  let zoomCaption = "";

  //added arrows for gal images
  function nextZoomImage() {
    const len = selected.images.length;
    const nextIndex = (selected.images.indexOf(zoomSrc) + 1) % len;
    zoomSrc = selected.images[nextIndex];
    zoomCaption = selected.captions?.[nextIndex] || "";
  }

  function prevZoomImage() {
    const len = selected.images.length;
    const prevIndex = (selected.images.indexOf(zoomSrc) - 1 + len) % len;
    zoomSrc = selected.images[prevIndex];
    zoomCaption = selected.captions?.[prevIndex] || "";
  }


  function openProject(id) {
    expanded = id;
    galleryIndex = 0;
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function closeProject() {
    expanded = null;
    galleryIndex = 0;
  }

  function showImage(i) {
    galleryIndex = i;
  }

  // image navigation (wrap-around)
  function nextImage() {
    if (!selected) return;
    const len = (selected.images?.length || 1);
    galleryIndex = (galleryIndex + 1) % len;
  }

  function prevImage() {
    if (!selected) return;
    const len = (selected.images?.length || 1);
    galleryIndex = (galleryIndex - 1 + len) % len;
  }

  // keyboard support for gallery and escape to close
  function onKeydown(e) {
    if (!selected) return;
    if (e.key === 'Escape') closeProject();
    if (e.key === 'ArrowRight') nextImage();
    if (e.key === 'ArrowLeft') prevImage();
  }

  $: {
    if (selected) {
      window.addEventListener('keydown', onKeydown);
    } else {
      window.removeEventListener('keydown', onKeydown);
    }
  }
</script>

<main class="container">
  <!-- Header-->
  <header class="projects-header">
    <div class="header-bar">
      <h1 class="title">Projects</h1>
      <nav class="nav">
        <a href="/" on:click|preventDefault={() => navigate('/')}>Home</a>
        <a href="/about" on:click|preventDefault={() => navigate('/about')}>About</a>
        <a href="/projects" on:click|preventDefault={() => navigate('/projects')}>Projects</a>
        <a href="/resume" on:click|preventDefault={() => navigate('/resume')}>Resume</a>
        <a href="/gallery" on:click|preventDefault={() => navigate('/gallery')}>Gallery</a>
      </nav>
    </div>
    <p class="subtitle">Click a project to open a detailed view with images, links, and notes.</p>
  </header>

  <section class="projects">
    {#if !selected}
      <h2 class="section-title">List of Projects</h2>
      <div class="project-list" role="list">
        {#each projects as project}
          <article class="project-row" role="listitem" on:click={() => openProject(project.id)}>
            {#if project.thumb}
              <img class="thumb" src={project.thumb} alt={`${project.title} thumbnail`} loading="lazy" />
            {:else}
              <div class="thumb placeholder" aria-hidden="true"></div>
            {/if}
            <div class="meta">
              <h3 class="proj-title">{project.title}</h3>
              <p class="preview">{project.preview}</p>
              <div class="row-meta">
                <span class="role">{project.role}</span>
                <span class="date">{project.date}</span>
              </div>
            </div>
          </article>
        {/each}
      </div>
    {:else}
      <!-- Focused project page -->
      <section class="project-focus" aria-live="polite">
        <div class="focus-controls">
          <button class="back-btn" on:click={closeProject}>← Back</button>

          {#if selected.images && selected.images.length > 1}
            <div class="nav-controls">
              <button class="nav-btn" on:click={prevImage} aria-label="Previous image">◀</button>
              <button class="nav-btn" on:click={nextImage} aria-label="Next image">▶</button>
            </div>
          {/if}
        </div>

        <header class="focus-header">
          <div class="focus-left">
            <h2 class="focus-title">{selected.title}</h2>

            <div class="meta-row">
              <span class="role">{selected.role}</span>
              <span class="date">{selected.date}</span>
              <div class="tags">
                {#each selected.tags ?? [] as t}
                  <span class="tag">{t}</span>
                {/each}
              </div>
            </div>

            <p class="lead">{selected.preview}</p>

            <div class="links">
              {#each selected.links ?? [] as link}
                <a class="link" href={link.href} target={link.external ? "_blank" : "_self"} rel={link.external ? "noopener noreferrer" : undefined}>
                  {link.label}
                </a>
              {/each}
            </div>

            <div class="tech">
              <strong>Tech:</strong> {selected.tech?.join(', ')}
            </div>
          </div>

          <!-- Gallery -->
          <div class="gallery" aria-hidden={selected.images?.length ? "false" : "true"}>
            {#if selected.images && selected.images.length > 0}
              <div class="main-image-wrap">
                <img
                  class="main-image"
                  src={selected.images[galleryIndex]}
                  alt={selected.captions?.[galleryIndex] || ""}
                  loading="lazy"
                  on:click={() => {
                    zoomSrc = selected.images[galleryIndex];
                    zoomCaption = selected.captions?.[galleryIndex] || "";
                    isZoomed = true;
                  }}
                  style="cursor: zoom-in;"
                />
              </div>
              <div class="thumb-row">
                {#each selected.images as img, i}
                  <button class="thumb-btn {i === galleryIndex ? 'active' : ''}" on:click={() => showImage(i)} aria-label={"Show image " + (i+1)}>
                    <img src={img} alt="" loading="lazy" />
                  </button>
                {/each}
              </div>
            {:else}
              <div class="no-image">No images for this project</div>
            {/if}
          </div>
        </header>

        <article class="focus-body">
          {#each selected.content as paragraph}
            <p>{paragraph}</p>
          {/each}

          {#if selected.bullets && selected.bullets.length}
            <ul>
              {#each selected.bullets as b}
                <li>{b}</li>
              {/each}
            </ul>
          {/if}

          {#if selected.codeUrl}
            <CodePanel codeUrl={selected.codeUrl} />
          {/if}

          {#if selected.embed}
            <div class="embed" innerHTML={selected.embed}></div>
          {/if}

        </article>
      </section>
    {/if}
  </section>
</main>

{#if isZoomed}
  <div class="zoom-modal" on:click={() => (isZoomed = false)}>
    <div class="zoom-content" on:click|stopPropagation>
      
      {#if selected.images.length > 1}
        <button class="zoom-arrow left" on:click={() => prevZoomImage()}>
          ◀
        </button>
      {/if}

      <img class="zoom-img" src={zoomSrc} alt={zoomCaption} />

      {#if selected.images.length > 1}
        <button class="zoom-arrow right" on:click={() => nextZoomImage()}>
          ▶
        </button>
      {/if}

      <p class="zoom-caption">{zoomCaption}</p>
    </div>
  </div>
{/if}


<style>
  .header-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .title {
    font-family: 'Imperial Script', cursive;
    font-size: 3.5rem;
    margin: 0;
    color: #0b2545;
  }

  .subtitle {
    font-size: 1.2rem;
    color: #567;
    margin-top: 0.5rem;
  }

  .nav {
    display: flex;
    gap: 1.5rem;
    font-weight: 500;
  }

  .nav a {
    color: #567;
    text-decoration: none;
  }

  .nav a:hover {
    text-decoration: underline;
  }

  .projects { margin-top: 1.5rem; }

  .section-title { margin: 0 0 0.75rem 0; color: #0b2545; }

  .project-list {
    display: flex;
    flex-direction: column;
    gap: 0.9rem;
    max-height: 60vh;
    overflow-y: auto;
    padding-right: 0.5rem;
  }

  .project-row {
    display: flex;
    gap: 0.9rem;
    align-items: center;
    padding: 0.6rem;
    border-radius: 8px;
    background: #fafafa;
    border: 1px solid #e6e6e6;
    cursor: pointer;
    transition: transform 0.12s ease, box-shadow 0.12s ease;
  }
  .project-row:hover { transform: translateY(-3px); box-shadow: 0 6px 18px rgba(0,0,0,0.06); }

  .thumb { width: 100px; height: 100px; object-fit: cover; border-radius: 6px; flex: 0 0 72px; box-shadow: 0 2px 6px rgba(0,0,0,0.08); }
  .thumb.placeholder { background: linear-gradient(135deg,#eee,#f7f7f7); }

  .meta { display:flex; flex-direction:column; min-width:0; }
  .proj-title {
    margin:0;
    font-size:1.05rem;
    color:#0b2545;
    white-space:nowrap;
    overflow:hidden;
    text-overflow:ellipsis;
  }

  .preview {
    margin:0.25rem 0 0;
    color:#334155;
    font-size:0.9rem;
    display:-webkit-box;
    -webkit-line-clamp:2;
    -webkit-box-orient:vertical;
    overflow:hidden;
  }

  .row-meta { margin-top:0.4rem; display:flex; gap:0.6rem; align-items:center; color:#567; font-size:0.85rem; }
  .role { font-weight:600; color:#234; }
  .date { color:#567; }

  .project-focus { margin-top:1rem; padding:1rem; background:#fff; border-radius:8px; border:1px solid #e6e6e6; }
  .focus-controls { display:flex; justify-content:space-between; align-items:center; gap:1rem; margin-bottom:0.75rem; }
  .back-btn { background:none; border:2px solid #567; color:#567; padding:0.4rem 0.8rem; border-radius:6px; cursor:pointer; font-weight:600; }
  .nav-controls { display:flex; gap:0.5rem; }
  .nav-btn { background:#f5f5f5; border:1px solid #ddd; padding:0.3rem 0.6rem; border-radius:6px; cursor:pointer; }

  .focus-header { display:flex; gap:1.25rem; align-items:flex-start; flex-wrap:wrap; }
  .focus-left { flex:1 1 360px; min-width:260px; }
  .focus-title { margin:0 0 0.25rem 0; color:#0b2545; font-size:1.6rem; }
  .meta-row { display:flex; gap:0.6rem; align-items:center; margin-bottom:0.5rem; flex-wrap:wrap; }
  .tags { display:flex; gap:0.4rem; }
  .tag { background:#f0f6ff; color:#0b2545; padding:0.15rem 0.5rem; border-radius:6px; font-size:0.8rem; }

  .lead { margin:0 0 0.75rem 0; color:#334155; }

  .links { display:flex; gap:0.6rem; flex-wrap:wrap; margin-bottom:0.5rem; }
  .link { color:#0b2545; text-decoration:underline; font-weight:600; }

  .tech { color:#334155; font-size:0.95rem; margin-top:0.5rem; }

  .gallery { width:320px; max-width:40%; min-width:220px; display:flex; flex-direction:column; gap:0.5rem; }
  .main-image-wrap { background:#f7f7f7; border-radius:8px; overflow:hidden; display:flex; align-items:center; justify-content:center; height:200px; }
  .main-image { width:100%; height:100%; object-fit:cover; display:block; }
  .thumb-row { display:flex; gap:0.4rem; margin-top:0.4rem; overflow-x:auto; }
  .thumb-btn { border:1px solid #eee; padding:0; background:#fff; border-radius:6px; cursor:pointer; }
  .thumb-btn img { width:64px; height:48px; object-fit:cover; display:block; border-radius:6px; }
  .thumb-btn.active { outline:3px solid rgba(11,37,69,0.12); }

  .no-image { color:#567; padding:1rem; border-radius:6px; background:#fafafa; }

  .focus-body { margin-top:1rem; color:#444; line-height:1.6; }
  .focus-body ul { margin-left:1.2rem; }

  /* responsive */
  @media (max-width: 900px) {
    .focus-header { flex-direction:column; }
    .gallery { width:100%; max-width:100%; min-width:0; }
    .main-image-wrap { height:220px; }
  }

  .zoom-modal {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.85);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 999999;
    pointer-events: auto;
  }

  .zoom-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  .zoom-caption {
    color: whitesmoke;
    font-size: 1rem;
    text-align: center;
    max-width: 80%;
  }

  .zoom-img {
    max-width: 90vw;
    max-height: 80vh;
    border-radius: 8px;
    box-shadow: 0 0 20px rgba(0,0,0,0.5);
    object-fit: contain;
  }

  .zoom-arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255,255,255,0.2);
    border: none;
    color: white;
    font-size: 2rem;
    padding: 8px 12px;
    cursor: pointer;
    border-radius: 6px;
    z-index: 1000000;
  }

  .zoom-arrow.left {
    left: 20px;
  }

  .zoom-arrow.right {
    right: 20px;
  }

  .zoom-arrow:hover {
    background: rgba(255,255,255,0.35);
  }


</style>
