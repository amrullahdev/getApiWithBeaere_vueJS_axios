methods:{
            loadDaftarUser(){
                const TOKEN = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiY2NkMWJiMWEyNDRjOTQ0ZTBlMGJjM2JiOWY3MjBmN2UyNjA5YTNhYzYwYWYzZDc5NTljN2RhYTU4YmMzNDc1Yjk5NTY5Zjg1NGQ5MDFjZWQiLCJpYXQiOjE2MDAxODIzNjIsIm5iZiI6MTYwMDE4MjM2MiwiZXhwIjoxNjMxNzE4MzYyLCJzdWIiOiIxIiwic2NvcGVzIjpbXX0.SBFmEUdZr2qNhAu_X8YRIS-ZXETv4YKl5_hAoA7ZSzgU4iVmRp7IebX0ADnq_0E_PH90sa6F4gtlYDHfTWJQi7PSSsJhJeYeWntilXw-ofFo4NY1HciR323PrFbsSaXqp2B7Gb9aNtUrLaTzGpcgozN747a613XhSc4Q_Su06GgXRcREQ79NENwyW1k0uzURKwfJ72BrDOgmbNjYfhUB5J2UxMT_bayuHAgFcSDAkCQ-xetWC2iGZBnoQEq3KZs0zrPfOoVw8Qw42F7iy5TuMAtFSKcOT9KUsdYEVp-m6ea4dwd9wt969MiAqEdFkNlO652f1bM6RDJRkU7JN5JTCT40NLltGyVwkJLRN9on1Zr6ppxjw2U1NzExlVyNiP6JSWIllGU2FD14Q53GRy9Bi49yY-2wItEWBw6AajanxJUhuVj6M6q10fU8JKRrIQtrt4BclVMtGHhw6KTINzBuVreD1P5-onN2nQqrxrTQigXBTMGdroh1dYpzrxZ0oNEqH1uR67kPI7hGFDpQGeQdeSDCndxFl1UOxos953hB6JcADpghmeSHK6mh4vy7vDjlO4EaDm_GBq7749eFbGG5zuZ4idND2w-rpKnChZi2dPqWtIvfnePTPNO4-JTmxDoTUS_kl6KaJnM-Jz-IvcYjwC8AMsMnsul_3H1tj5FLmTM';
                const BASEURL = 'http://127.0.0.1:8081';
                const ENDPOINT = '/api/user';

                this.$Progress.start()
                axios.create({
                    baseURL: BASEURL,
                     headers: {
                        'Content-Type': 'application/json',
                        'Authorization': 'Bearer '+TOKEN
                    }
                }).get(ENDPOINT)

                axios.create({
                        baseURL: BASEURL,
                        headers: {
                            'Content-Type': 'application/json',
                            'Authorization': 'Bearer '+TOKEN
                        }
                    })
                    .get(ENDPOINT)
                    .then( ({data})=>(this.variableToLoadData = data) )
                    .then(()=>{
                            this.$Progress.finish();
                        })
                        .catch(()=>{
                            this.$Progress.fail();
                        })                    

            },