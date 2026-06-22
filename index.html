// A dedicated, independent HTTP storage bucket for the DE TEAM portal
const KV_BUCKET_URL = "https://kvdb.io/K99b6BBN2x58pC6SUpXN9U/acca_de_workspaces";

// Default pre-seeded markets tailored specifically for the DE/DACH division
const defaultMarkets = [
  {name:"Deutschland", city:"Frankfurt", code:"de", img:"https://images.unsplash.com/photo-1467269204594-9661b134dd2b?w=1200", url:"#", custom:false},
  {name:"Österreich", city:"Wien", code:"at", img:"https://images.unsplash.com/photo-1516550360452-9312f5e86fc7?w=1200", url:"#", custom:false},
  {name:"Schweiz", city:"Zürich", code:"ch", img:"https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?w=1200", url:"#", custom:false}
];

export default async function handler(request, response) {
  try {
    const { method } = request;

    // --- GET: FETCH DE WORKSPACES ---
    if (method === 'GET') {
      const res = await fetch(KV_BUCKET_URL);
      
      if (res.status === 404) {
        await fetch(KV_BUCKET_URL, {
          method: 'POST',
          body: JSON.stringify(defaultMarkets)
        });
        return response.status(200).json(defaultMarkets);
      }

      const data = await res.json();
      return response.status(200).json(data);
    }

    // --- POST: ADD NEW DE WORKSPACE ---
    if (method === 'POST') {
      const newWorkspace = request.body;
      const getRes = await fetch(KV_BUCKET_URL);
      let currentData = getRes.status === 200 ? await getRes.json() : defaultMarkets;

      currentData.push(newWorkspace);
      
      await fetch(KV_BUCKET_URL, {
        method: 'POST',
        body: JSON.stringify(currentData)
      });
      return response.status(200).json(currentData);
    }

    // --- DELETE: REMOVE DE WORKSPACE ---
    if (method === 'DELETE') {
      const { index } = request.query;
      const getRes = await fetch(KV_BUCKET_URL);
      let currentData = getRes.status === 200 ? await getRes.json() : defaultMarkets;

      if (index !== undefined) {
        currentData.splice(parseInt(index, 10), 1);
        await fetch(KV_BUCKET_URL, {
          method: 'POST',
          body: JSON.stringify(currentData)
        });
      }
      return response.status(200).json(currentData);
    }

    return response.status(405).json({ error: "Method not allowed" });

  } catch (error) {
    return response.status(500).json({ error: error.message });
  }
}
