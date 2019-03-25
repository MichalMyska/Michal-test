const express = require('express');
const app = express();
const port = 3000


const countries = [
    { id: 1, state: "Germany", people: 80000000, capitol: 'Berlin', area: 350000},
    { id: 2, state: "Poland", people: 40000000, capitol: 'Warszawa' , area: 300000},
    { id: 3, state: "Slovakia", people: 5000000, capitol: 'Bratislava', area: 40000 },
    { id: 4, state: "Hungary", people: 9900000, capitol: 'Budapest', area: 100000 },
];

app.get('/countries',(req,res) => {res.send(countries)});

app.get('/countries/:id', (req,res) => {
    const id = Number(req.params.id);
    const country = countries.find( country => country.id === id);
    if (country) {res.send (country);}
 else {res.status (404).send('prdlajs');}

    });

app.get('/countries/:state', (req,res) =>  {
  const country = (courses.find(c => c.id === parseInt(req.params.id));
    if(!country) res.status(404).send ('prd')
    }));


app.listen(port, () => console.log(`Example app listening on port ${port}!`))
