# React

#### Hands on

---

# Project 1

---

## Show Finder

![result](./Screen&#32;Shot&#32;2019-12-19&#32;at&#32;17.58.29.png)

---

## Step 1

create a new project

```sh
npx create-react-app --template typescript react-shows
```

---

## Step 2

Create `Header` and `List` and `Tile` components

---

## Step 3

Add mock data (taken from http://api.tvmaze.com/search/shows?q=lost)

```typescript
export const shows: any[] = [
    {
        score: 18.282442,
        show: {
            id: 123,
            url: 'http://www.tvmaze.com/shows/123/lost',
            name: 'Lost',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Adventure', 'Supernatural'],
            status: 'Ended',
            runtime: 60,
            premiered: '2004-09-22',
            officialSite: 'http://abc.go.com/shows/lost',
            schedule: {
                time: '21:00',
                days: ['Tuesday'],
            },
            rating: {
                average: 8.4,
            },
            weight: 90,
            network: {
                id: 3,
                name: 'ABC',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: 4284,
                thetvdb: 73739,
                imdb: 'tt0411008',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/0/1389.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/0/1389.jpg',
            },
            summary:
                "<p>Out of the blackness, the first thing Jack senses is pain. Then burning sun. A Bamboo forest. Smoke. Screams. With a rush comes the horrible awareness that the plane he was on tore apart in mid-air and crashed on a Pacific island. From there it's a blur, as his doctor's instinct kicks in: people need his help.</p><p>Stripped of everything, the 48 survivors scavenge what they can from the plane for their survival. Some panic. Some pin their hopes on rescue. A few find inner strength they never knew they had -- like Kate, who, with no medical training, suddenly finds herself suturing the doctor's wounds. Hurley - a man with a warm sense of humor despite the desperate situation - does his best to keep his cool as he helps those around him to survive. Charlie is a faded rock star who harbors a painful secret. Sayid is a Middle Eastern man who must wrestle with the racial profiling directed at him by some of his fellow survivors. Jin and Sun are a Korean couple whose traditions, values and language are foreign, and thus causes much to get lost in the translation. Sawyer has an air of danger surrounding him, and his intense sense of mistrust for everyone around him could prove to be fatal to his fellow castaways. Michael has just gained custody of his nine-year-old son, Walt, after the death of his ex-wife - they are a father and son who don't even know each other. Locke is a mysterious man who keeps to himself, and who harbors a deeper connection to the island than any of the others. Self-centered Shannon - who actually gives herself a pedicure amid the chaos - and her estranged controlling brother, Boone , constantly bicker and must learn to get along if they are to survive. And young Claire is eight months pregnant and ill-prepared for the hardships of motherhood - especially on a deserted island.</p>",
            updated: 1575600365,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/123',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/10260',
                },
            },
        },
    },
    {
        score: 15.544834,
        show: {
            id: 17377,
            url: 'http://www.tvmaze.com/shows/17377/lost',
            name: 'Lost',
            type: 'Reality',
            language: null,
            genres: [],
            status: 'Ended',
            runtime: 60,
            premiered: '2001-09-05',
            officialSite: null,
            schedule: {
                time: '',
                days: [],
            },
            rating: {
                average: null,
            },
            weight: 63,
            network: {
                id: 1,
                name: 'NBC',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: 72906,
                imdb: null,
            },
            image: null,
            summary:
                '<p>Three pairs of globe-trotting strangers must work together to be the first team to reach the Statue of Liberty from a secret drop location. The winners will split the prize of $200,000. Over the life of the series, two different adventures were scheduled to take place.</p>',
            updated: 1574818194,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/17377',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/792031',
                },
            },
        },
    },
    {
        score: 14.176984,
        show: {
            id: 44956,
            url: 'http://www.tvmaze.com/shows/44956/lost-secrets',
            name: 'Lost Secrets',
            type: 'Documentary',
            language: 'English',
            genres: ['History'],
            status: 'Running',
            runtime: 60,
            premiered: '2019-11-10',
            officialSite: 'https://www.travelchannel.com/shows/lost-secrets',
            schedule: {
                time: '23:00',
                days: ['Sunday'],
            },
            rating: {
                average: 5.3,
            },
            weight: 98,
            network: {
                id: 82,
                name: 'Travel Channel',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: 371653,
                imdb: null,
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/221/553072.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/221/553072.jpg',
            },
            summary:
                "<p>Historian and Wende Museum founder Justin Jampol unlocks the secrets of the past through recently unearthed artifacts. Using state-of-the-art scientific testing and good old-fashioned detective work, Justin's investigations reveal new understandings about some of the most significant moments in history.</p>",
            updated: 1574610741,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/44956',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/1762009',
                },
            },
        },
    },
    {
        score: 13.484484,
        show: {
            id: 503,
            url: 'http://www.tvmaze.com/shows/503/the-lost-room',
            name: 'The Lost Room',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Science-Fiction', 'Thriller'],
            status: 'Ended',
            runtime: 90,
            premiered: '2006-12-11',
            officialSite: null,
            schedule: {
                time: '21:00',
                days: ['Wednesday'],
            },
            rating: {
                average: 8.1,
            },
            weight: 76,
            network: {
                id: 16,
                name: 'Syfy',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: 14688,
                thetvdb: 79637,
                imdb: 'tt0830361',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/4/10835.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/4/10835.jpg',
            },
            summary:
                '<p>A mysterious event at the Sunshine Motel caused ordinary things in Room 10 to transform into indestructible objects with extraordinary powers. Detective Joe Miller discovers the dangerous potential of these objects when his daughter becomes lost in the room. His only hope of saving her is to find The Key, but shadowy figures will stop at nothing to keep it - and the other objects - for themselves.</p>',
            updated: 1573686068,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/503',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/45905',
                },
            },
        },
    },
    {
        score: 13.145519,
        show: {
            id: 12,
            url: 'http://www.tvmaze.com/shows/12/lost-girl',
            name: 'Lost Girl',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Fantasy', 'Horror'],
            status: 'Ended',
            runtime: 60,
            premiered: '2010-09-12',
            officialSite: 'http://www.showcase.ca/lostgirl',
            schedule: {
                time: '22:00',
                days: ['Sunday'],
            },
            rating: {
                average: 8.2,
            },
            weight: 87,
            network: {
                id: 6,
                name: 'Showcase',
                country: {
                    name: 'Canada',
                    code: 'CA',
                    timezone: 'America/Halifax',
                },
            },
            webChannel: null,
            externals: {
                tvrage: 26401,
                thetvdb: 182061,
                imdb: 'tt1429449',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/0/137.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/0/137.jpg',
            },
            summary:
                '<p><b>Lost Girl</b> follows supernatural seductress Bo, a Succubus who feeds on the sexual energy of humans. Growing up with human parents, Bo had no reason to believe she was anything other than the girl next door — until she drained her boyfriend to death in their first sexual encounter. Now she has hit the road alone and afraid. <br /> She discovers she is one of the Fae, creatures of legend and folklore, who pass as humans while feeding off them secretly and in different ways, as they have for millennia. Relieved yet horrified to find out that she is not alone, Bo decides to take the middle path between the humans and the Fae while embarking on a personal mission to unlock the secrets of her origin.</p><p>With the help of her human sidekick, Kenzi, and Dyson, a sexy police detective, Bo takes on a challenge every week helping a Fae or human client who comes to her to solve a mystery, or to right a wrong.</p>',
            updated: 1573154728,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/12',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/316120',
                },
            },
        },
    },
    {
        score: 13.09539,
        show: {
            id: 45311,
            url: 'http://www.tvmaze.com/shows/45311/the-lost-world',
            name: 'The Lost World',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Adventure', 'Science-Fiction'],
            status: 'Ended',
            runtime: 75,
            premiered: '2001-12-25',
            officialSite: 'http://www.bbc.co.uk/drama/lostworld/',
            schedule: {
                time: '',
                days: ['Tuesday', 'Wednesday'],
            },
            rating: {
                average: null,
            },
            weight: 88,
            network: {
                id: 12,
                name: 'BBC One',
                country: {
                    name: 'United Kingdom',
                    code: 'GB',
                    timezone: 'Europe/London',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: null,
                imdb: 'tt0302739',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/229/574004.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/229/574004.jpg',
            },
            summary:
                '<p>Professor Challenger, on an expedition to South America, shoots an animal that he claims is a pre-historic pterosaur. On his return to England, his fellow Professor, Summerlee, and most of the scientific establishment dismiss it as a hoax. However, an ambitious hunter and womaniser John Roxton and journalist Edward Malone are prepared to undertake the mission to find the truth. Challenger, Summerlee, Roxton and Malone set off for a Brazilian plateau in search of pre-historic life.</p>',
            updated: 1575599441,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/45311',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/1768710',
                },
            },
        },
    },
    {
        score: 13.089764,
        show: {
            id: 45021,
            url: 'http://www.tvmaze.com/shows/45021/the-lost-corvettes',
            name: 'The Lost Corvettes',
            type: 'Reality',
            language: 'English',
            genres: [],
            status: 'Running',
            runtime: 30,
            premiered: '2019-11-09',
            officialSite:
                'https://www.fyi.tv/shows/the-lost-corvettes?newexp=true',
            schedule: {
                time: '22:00',
                days: ['Saturday'],
            },
            rating: {
                average: null,
            },
            weight: 95,
            network: {
                id: 125,
                name: 'fyi,',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: 372231,
                imdb: 'tt10642858',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/223/558965.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/223/558965.jpg',
            },
            summary:
                '<p>In the history of automotive discoveries, very few can match the "barn find" of the Peter Max Collection of vintage Corvettes. Thirty-six Corvettes -- one from each year -- are discovered covered in dust in a New York City garage. Now, Corvette restorer and collector Chris Mazzilli and his team at Dream Car Restoration are taking on the challenge of restoring these legendary vehicles to their former glory. In <b>The Lost Corvettes</b> series, Chris and his team rehab the most important, the most iconic and the most valuable cars in this one-of-a-kind collection, focusing on the models with the most history and the most challenging restoration hurdles. Tracking down engine parts, adding horsepower and trying to recreate styles that have been discontinued, Chris and his team have their work cut out for them. After the series, viewers will have a chance to win each and every one of these 36 American classics in "The Lost Corvettes" Giveaway.</p>',
            updated: 1573828565,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/45021',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/1756765',
                },
            },
        },
    },
    {
        score: 12.297942,
        show: {
            id: 42564,
            url: 'http://www.tvmaze.com/shows/42564/paradise-lost',
            name: 'Paradise Lost',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Mystery'],
            status: 'In Development',
            runtime: 60,
            premiered: null,
            officialSite: null,
            schedule: {
                time: '',
                days: [],
            },
            rating: {
                average: null,
            },
            weight: 88,
            network: {
                id: 1620,
                name: 'Spectrum',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: null,
                imdb: null,
            },
            image: null,
            summary:
                "<p><b>Paradise Lost</b> is about a psychiatrist who moves with her family from California to her husband's hometown in Mississippi only to uncover shameful secrets that irrevocably change the lives of everyone involved.</p>",
            updated: 1560280109,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/42564',
                },
            },
        },
    },
    {
        score: 11.936218,
        show: {
            id: 23176,
            url: 'http://www.tvmaze.com/shows/23176/lost-survivors',
            name: 'Lost Survivors',
            type: 'Reality',
            language: 'English',
            genres: [],
            status: 'Ended',
            runtime: 60,
            premiered: '2013-11-12',
            officialSite: null,
            schedule: {
                time: '23:00',
                days: ['Tuesday'],
            },
            rating: {
                average: null,
            },
            weight: 0,
            network: {
                id: 82,
                name: 'Travel Channel',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: 276667,
                imdb: 'tt3339282',
            },
            image: {
                medium:
                    'http://static.tvmaze.com/uploads/images/medium_portrait/86/216601.jpg',
                original:
                    'http://static.tvmaze.com/uploads/images/original_untouched/86/216601.jpg',
            },
            summary:
                '<p>Married survival experts test their skills when they are left stranded in an undisclosed location with minimal supplies and few clues as to how to get back to civilization.</p>',
            updated: 1480369574,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/23176',
                },
                previousepisode: {
                    href: 'http://api.tvmaze.com/episodes/999999',
                },
            },
        },
    },
    {
        score: 11.886924,
        show: {
            id: 20222,
            url: 'http://www.tvmaze.com/shows/20222/the-lost-boys',
            name: 'The Lost Boys',
            type: 'Scripted',
            language: 'English',
            genres: ['Drama', 'Action', 'Horror'],
            status: 'In Development',
            runtime: 60,
            premiered: null,
            officialSite: null,
            schedule: {
                time: '',
                days: [],
            },
            rating: {
                average: null,
            },
            weight: 49,
            network: {
                id: 5,
                name: 'The CW',
                country: {
                    name: 'United States',
                    code: 'US',
                    timezone: 'America/New_York',
                },
            },
            webChannel: null,
            externals: {
                tvrage: null,
                thetvdb: null,
                imdb: null,
            },
            image: null,
            summary:
                '<p><b>The Lost Boys </b>is a series adaptation of the iconic 1987 Warner Bros horror comedy feature film of the same name. Envisioned for a seven-season, anthology-style run, the series will tell a story spanning 70 years, each season chronicling a decade. Season 1 will be set in San Francisco during the Summer of Love, 1967. Each season, the humans, the setting, the antagonist and the story all change — only the vampires, our Lost Boys, who like the Peter Pan characters never grow up, remain the same. The project, will explore what it really means to be immortal.</p>',
            updated: 1561791140,
            _links: {
                self: {
                    href: 'http://api.tvmaze.com/shows/20222',
                },
            },
        },
    },
];

```


---

## Step 4

Transform the data into a format that suits our components

---

## Transformation function

```typescript
function formatRawShows(item: any): Item {
    const { score, show } = item;
    return {
        id: show.id,
        pic: show.image ? show.image.medium : '', // unsafe...
        title: show.name,
        score,
        description: show.summary,
    };
}
```

---

## Step 5

Populate the list component

---

```typescript
// App.tsx
import React, { ChangeEvent } from 'react';
import Header from './components/header/Header';
import List from './components/list/List';
import { TileTypes, Item } from './types';
import './App.css';
import { shows as rawShows } from './mocks';

// Mock data
// TODO - replace with real
const shows: Item[] = rawShows
    .filter(show => show.show.image)
    .map(formatRawShows);

function formatRawShows(item: any): Item {
    const { score, show } = item;
    return {
        id: show.id,
        pic: show.image ? show.image.medium : '', // unsafe...
        title: show.name,
        score,
        description: show.summary,
    };
}

interface Props {}

interface State {}

class App extends React.Component<Props, State> {
    
    render() {
        return (
            <div className="App">
                <Header />
                <List items={shows} />
            </div>
        );
    }
}

export default App;

```

---

## Step 6

Add state to the "container" `App.tsx`

- `q: string` - for storing the query
- `shows: Item[]` - for storing the shows' data

also add functions to update the state

---

## Step 7

Replace the mock data with a real api call

- use this free api: `http://api.tvmaze.com/search/shows?q=${query}`
- use [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- the fetching of new data should happen every time the search query changes
  
---

## Step 8

Try to make it look more appealing :) with basic CSS

---

Compare to my code - https://github.com/jsBlackBelt/react-shows/tree/step2


