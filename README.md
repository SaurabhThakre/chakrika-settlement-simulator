# Chakrika Settlement Simulator

Chakrika is an interactive IIM Bangalore Fintech project that demonstrates how circular B2B invoices can be netted and settled using a simulated programmable digital rupee (e₹) and an NBFC liquidity bridge.

**[Open the simulator](https://saurabhthakre.github.io/chakrika-settlement-simulator/)**

## Run the demo

1. Select **PEENYA-094** and leave **NBFC Δ-Bridge (100%)** selected. The four-hop ring contains ₹42 lakh of post-TDS payables. It needs ₹4 lakh of external bridge credit plus a reusable ₹9 lakh flash seed.
2. Use the five phase buttons, **Step Forward**, or **Auto-Run**. In **Auto** graph view, the full cluster gives way to an SGX-highlighted cycle and then the isolated clearing ring. Watch the liquidity vectors, hop locks, and settlement receipts appear as the run progresses.
3. Switch to **Bottleneck** and repeat. The same ₹9 lakh flash seed clears ₹36 lakh across four hops with zero external credit, leaving ₹6 lakh outstanding. Check the difference between **PAID** and **PART** in the invoice table.
4. Reset and enable **Fault**. Advance through execution or jump to the statutory ledger to see the timeout. Step once more to roll back the provisional locks.
5. Explore the other clusters or add, edit, and delete invoices. Try removing **IRN-412** in Peenya, then adding a closing invoice or restoring the default cluster.

## What’s included

- Four sample industrial clusters, live Tarjan SCC and elementary cycle detection, and a ring selector for the Chakan network.
- Two clearing modes, three TDS regimes, an invoice-age risk filter, and editable invoice scenarios.
- An interactive illustrated graph with zoom, pan, draggable nodes, and invoice and firm inspectors.
- Liquidity and ROE metrics, a copyable token payload, hop-by-hop HTLC and audit logs, and a simulated GST/UTR ledger and Key Facts Statement.

## Sample data

The original standalone HTML is the source for the sample invoice values. Some worked figures in the specification describe a different set of invoices.

| Cluster | Ring | Post-TDS payables | External Δ-Bridge | Flash seed |
| --- | --- | ---: | ---: | ---: |
| PEENYA-094 | 4 hops | ₹42.00L | ₹4.00L | ₹9.00L |
| TIRUPPUR-208 | 5 hops | ₹66.00L | ₹5.50L | ₹11.50L |
| CHAKAN-315 | 4 hops | ₹63.50L | ₹4.50L | ₹14.50L |
| CHAKAN-315 | 3 hops | ₹36.00L | ₹9.50L | ₹8.50L |
| SURAT-402 | 4 hops | ₹80.00L | ₹1.00L | ₹19.50L |

## Scope

This is an educational simulation. The public build uses fictional firm names, bank labels, tax and registration identifiers, and wallet addresses. CBDC transfers, bank switches, SGX, HTLCs, UTRs, certificates, and lending disclosures are modeled in the browser. The Chakan rings share an invoice and run as separate scenarios. The specification’s production design for sequential residual clearing and simultaneous voucher splitting is outside this simulator.

## Run locally

Open `index.html` in a browser. The simulator has no build step, backend, or runtime JavaScript dependencies. Web fonts are optional and fall back to system fonts when offline. Invoice edits are held in memory for the current session.

GitHub Pages serves `index.html` from the root of the `main` branch.
