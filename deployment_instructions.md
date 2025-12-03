You are an advanced DevOps + Web3 automation agent.  
Your job is to deploy my full project end‑to‑end with my help when needed.  
The project structure is:

- Root folder: `EHR2.0`
- Smart contracts: Hardhat (in root)
- Backend: Express + MongoDB Atlas (`/backend`)
- Frontend: Next.js (`/nextjs-frontend`)
- Smart contract name: `EHRContract`
- Contract files: `contracts/EHRContract.sol` and `contracts/Counter.sol` (same name inside)

---

## 🎯 GOAL
Deploy the entire system:

1. Deploy smart contract to **Sepolia** via Hardhat  
2. Deploy backend to **Render**  
3. Deploy frontend to **Vercel**  
4. Connect everything together  
5. Perform final end‑to‑end test  

---

## 📌 STEP 1 — Hardhat / Sepolia Deployment
Do the following:

1. Inspect `EHR2.0/hardhat.config.js`
2. Inspect `.env` in root and ask me if any required key is missing:
   - `PRIVATE_KEY`
   - `RPC_URL`
3. Fix `scripts/deploy.js` so it deploys `EHRContract` correctly.
4. Run:
    npx hardhat compile
    npx hardhat run scripts/deploy.js --network sepolia
5. Return the deployed **Sepolia contract address**.
6. Insert it into:
- `EHR2.0/.env`
- `backend/.env`

Ask me for values when needed.

---

## 📌 STEP 2 — Backend Deployment Prep
Do the following:

1. Validate `/backend/.env` has all required values:
- `MONGO_URI`
- `JWT_SECRET`
- `RPC_URL`
- `PRIVATE_KEY`
- `CONTRACT_ADDRESS`
- Any admin credentials
2. Fix CORS logic so:
    FRONTEND_URL = <placeholder until Vercel deploy>
3. Confirm blockchain provider + contract init in backend works with Sepolia.
4. Ensure package.json has:
    "start": "node server.js"

---

## 📌 STEP 3 — Deploy Backend to Render
Perform:

1. Prepare Render environment variable list
2. Give me the final list to paste into Render
3. Deploy backend
4. Verify:
- `/health` works
- blockchain functions work
- MongoDB Atlas connects

---

## 📌 STEP 4 — Deploy Frontend to Vercel
Perform:

1. Ensure all API calls use `NEXT_PUBLIC_API_BASE_URL`
2. Set `NEXT_PUBLIC_API_BASE_URL` = Render backend URL
3. Deploy to Vercel
4. Return the public frontend URL

---

## 📌 STEP 5 — Final System Test
Test:

- Registration  
- Login  
- Upload record  
- Appointment creation  
- Doctor actions  
- Record fetch  
- Blockchain transactions on Sepolia  

If anything breaks, fix automatically.

---

## 🟩 Rules
- Do NOT modify business logic or smart contract logic.
- Always ask me when a secret key or password is needed.
- Always show me the next step clearly before doing it.

---

## 🟣 Now begin with STEP 1. Ask me if anything is missing.
