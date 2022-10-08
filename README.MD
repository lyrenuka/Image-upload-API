# Image Uploader

Let's see if i've learnt enough to make one :)

## Technologies

Backend: Node.js / Express
FrontEnd: Next.js / tailwindcss
Database: Firestore
Authentication: Firebase
Hosting: Vercel
API: Repl.it ?

## Structure of the project

- Server
|- responsible for the api
- Dashboard
|- responsible for the frontend

## TODO (MVP)

- [X] Create a POST route /api/upload that accepts a file and returns the image url
- [X] Make sure a file can't have the same name as an existing file
- [X] Create a GET route /server/uploads/:filename that returns a html file with the image
- [X] Create a GET route /raw/:filename that returns the actual image
- [X] Create a POST route /api/delete that accepts a url and deletes the image
- [X] Create a GET route /api/images that returns a json response with all the images

## TODO (DASHBOARD)

- [ ] Create a dashboard that shows all the images
- [ ] Lists all images with a delete button, copy url button and a raw url button
- [ ] Upload form

## TODO (ADMIN)

- [X] Create a POST route /admin/createApikey that takes a admin key, username, email and creates a api key for the user and saves it to a database (firestore)
- [X] Create a GET route /admin/listKeys that lists every api key, who owns it and when it was created.
- [X] Create a POST route /admin/deleteKey that takes a api key and deletes it from the database (firestore)

## TODO (QOL)

- [X] Upload images to a firestore bucket
- [ ] Cleanup code
- [ ] Auth with API keys
- [ ] Add a admin panel

## TODO (BUGS)

- [X] const extension = req.files.file.name.split('.').pop(); this gon break on .tar.gz or on .js.map // use path.extname
- [ ] remove express-fileupload
- [ ] try to use promisified fs apis
- [X] fs.appendFileSync('./apikeys.txt', ${apiKey} ${username} ${email}\n); this could pose as some weird risk  / if I put \n / into the text / it might parse as newline
- [ ]  I recommend using headers/cookies / instead of body based auth / and just create an admin auth middleware
- [X] use hashed admin secrets not plain text
- [X] Replace these username === '' with username.trim() === ''
- [ ] do type checks
