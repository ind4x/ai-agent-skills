# Specialized Domains (Blockchain, Hardware, Math)

Domain-specific skills for EVM smart contract development, embedded IoT hardware (M5Stack, Cardputer), and formal mathematical proofs.

---

## Category Principles & Scope

- EVM smart contract security: deterministic compilation, automated unit testing with Viem/Ethers, and gas profiling.
- Embedded firmware hacking: ESP32 development, serial terminal debugging, and peripheral sensor integration.
- Formal mathematical reasoning: step-by-step theorem proving, Olympiad problem solving, and rigorous deduction.

---

## Skills Catalog

| Skill | Display Name | Core Purpose & Capabilities |
| :--- | :--- | :--- |
| [`cardputer-buddy`](./cardputer-buddy/SKILL.md) | **cardputer-buddy** | Iterate on the Cardputer-Adv MicroPython app bundle (Claude Buddy, Snake, Hello) after the device is already provisioned via m5-onboard. Use when the user wants to add a new app, push a single changed .py without re-flashing, watch device serial logs, or run a one-shot REPL command. Trigger on "add an app", "push to the cardputer", "tail the device", "run on the device", or follow-up work after /maker-setup. |
| [`hardhat`](./hardhat/SKILL.md) | **hardhat** | Use when working with Hardhat 3 projects — writing or modifying Solidity tests, TypeScript tests, or any code touching hardhat.config.ts, the `hardhat` import, or `network.create()`. Covers test-layer choice, forge-std cheatcodes, the network connection API, `networkHelpers`, and the compile-then-typecheck workflow. For toolbox-specific guidance (clients, contract calls, assertions), also load the matching `hardhat-toolbox-*` skill. |
| [`hardhat-toolbox-mocha-ethers`](./hardhat-toolbox-mocha-ethers/SKILL.md) | **hardhat-toolbox-mocha-ethers** | Use alongside the `hardhat` skill when the project depends on `@nomicfoundation/hardhat-toolbox-mocha-ethers`. Covers the ethers helpers exposed on `network.create()`, contract interaction (`ethers.deployContract`, calling functions, `connect`), TypeChain-typed contract instances, and the chai matchers from `@nomicfoundation/hardhat-ethers-chai-matchers` (`.to.emit`, `.to.be.revertedWith*`, `.to.changeEtherBalance(s)`). |
| [`hardhat-toolbox-viem`](./hardhat-toolbox-viem/SKILL.md) | **hardhat-toolbox-viem** | Use alongside the `hardhat` skill when the project depends on `@nomicfoundation/hardhat-toolbox-viem`. Covers the viem clients exposed on `network.create()`, contract interaction (`viem.deployContract`, `read`, `write`, `getContractAt`), and `viem.assertions` (revert / event / balance assertions). |
| [`m5-onboard`](./m5-onboard/SKILL.md) | **m5-onboard** | End-to-end onboarding for a freshly-plugged-in M5Stack ESP32 device (Cardputer, Cardputer-Adv, Core, CoreS3, Stick) — detect on USB, flash UIFlow 2.0 firmware, and install the Claude Buddy MicroPython app bundle. Use whenever the user plugs in or wants to flash/provision/reset an M5Stack or ESP32 board, or says "m5-onboard go". |
| [`math-olympiad`](./math-olympiad/SKILL.md) | **math-olympiad** | Solve competition math problems (IMO, Putnam, USAMO, AIME) with adversarial verification that catches the errors self-verification misses. Activates when asked to 'solve this IMO problem', 'prove this olympiad inequality', 'verify this competition proof', 'find a counterexample', 'is this proof correct', or for any problem with 'IMO', 'Putnam', 'USAMO', 'olympiad', or 'competition math' in it. Uses pure reasoning (no tools) — then a fresh-context adversarial verifier attacks the proof using specific failure patterns, not generic 'check logic'. Outputs calibrated confidence — will say 'no confident solution' rather than bluff. If LaTeX is available, produces a clean PDF after verification passes. |
| [`siege`](./siege/SKILL.md) | **siege** | Work on one hard mathematics problem in rounds: each round a judge writes a few self-contained questions, independent workers answer them, and the judge keeps a ledger of what is proved, refuted and open, until the judge concludes or the rounds run out, and then a proof.md says plainly what is and is not proved. A run takes hours and dozens of worker runs. Usage: /math-proof:siege [NAME=value settings] <the problem, stated in full, or the path of a file holding it>. |
| [`solo`](./solo/SKILL.md) | **solo** | Work on one hard mathematics problem in this session yourself, with no sub-agents: reason in stages, record each settled step in a notes file so that nothing written is lost if a response is cut off, and end with a self-contained proof.md. Usage: /math-proof:solo <the problem, stated in full, or the path of a file holding it>. |

---

## Detailed Skill Overviews

### [`cardputer-buddy`](./cardputer-buddy/SKILL.md)

- **Skill Identifier:** `cardputer-buddy`
- **Path:** [`specialized-domains/cardputer-buddy/`](./cardputer-buddy/)
- **Operational Summary:**
  Iterate on the Cardputer-Adv MicroPython app bundle (Claude Buddy, Snake, Hello) after the device is already provisioned via m5-onboard. Use when the user wants to add a new app, push a single changed .py without re-flashing, watch device serial logs, or run a one-shot REPL command. Trigger on "add an app", "push to the cardputer", "tail the device", "run on the device", or follow-up work after /maker-setup.

### [`hardhat`](./hardhat/SKILL.md)

- **Skill Identifier:** `hardhat`
- **Path:** [`specialized-domains/hardhat/`](./hardhat/)
- **Operational Summary:**
  Use when working with Hardhat 3 projects — writing or modifying Solidity tests, TypeScript tests, or any code touching hardhat.config.ts, the `hardhat` import, or `network.create()`. Covers test-layer choice, forge-std cheatcodes, the network connection API, `networkHelpers`, and the compile-then-typecheck workflow. For toolbox-specific guidance (clients, contract calls, assertions), also load the matching `hardhat-toolbox-*` skill.

### [`hardhat-toolbox-mocha-ethers`](./hardhat-toolbox-mocha-ethers/SKILL.md)

- **Skill Identifier:** `hardhat-toolbox-mocha-ethers`
- **Path:** [`specialized-domains/hardhat-toolbox-mocha-ethers/`](./hardhat-toolbox-mocha-ethers/)
- **Operational Summary:**
  Use alongside the `hardhat` skill when the project depends on `@nomicfoundation/hardhat-toolbox-mocha-ethers`. Covers the ethers helpers exposed on `network.create()`, contract interaction (`ethers.deployContract`, calling functions, `connect`), TypeChain-typed contract instances, and the chai matchers from `@nomicfoundation/hardhat-ethers-chai-matchers` (`.to.emit`, `.to.be.revertedWith*`, `.to.changeEtherBalance(s)`).

### [`hardhat-toolbox-viem`](./hardhat-toolbox-viem/SKILL.md)

- **Skill Identifier:** `hardhat-toolbox-viem`
- **Path:** [`specialized-domains/hardhat-toolbox-viem/`](./hardhat-toolbox-viem/)
- **Operational Summary:**
  Use alongside the `hardhat` skill when the project depends on `@nomicfoundation/hardhat-toolbox-viem`. Covers the viem clients exposed on `network.create()`, contract interaction (`viem.deployContract`, `read`, `write`, `getContractAt`), and `viem.assertions` (revert / event / balance assertions).

### [`m5-onboard`](./m5-onboard/SKILL.md)

- **Skill Identifier:** `m5-onboard`
- **Path:** [`specialized-domains/m5-onboard/`](./m5-onboard/)
- **Operational Summary:**
  End-to-end onboarding for a freshly-plugged-in M5Stack ESP32 device (Cardputer, Cardputer-Adv, Core, CoreS3, Stick) — detect on USB, flash UIFlow 2.0 firmware, and install the Claude Buddy MicroPython app bundle. Use whenever the user plugs in or wants to flash/provision/reset an M5Stack or ESP32 board, or says "m5-onboard go".

### [`math-olympiad`](./math-olympiad/SKILL.md)

- **Skill Identifier:** `math-olympiad`
- **Path:** [`specialized-domains/math-olympiad/`](./math-olympiad/)
- **Operational Summary:**
  Solve competition math problems (IMO, Putnam, USAMO, AIME) with adversarial verification that catches the errors self-verification misses. Activates when asked to 'solve this IMO problem', 'prove this olympiad inequality', 'verify this competition proof', 'find a counterexample', 'is this proof correct', or for any problem with 'IMO', 'Putnam', 'USAMO', 'olympiad', or 'competition math' in it. Uses pure reasoning (no tools) — then a fresh-context adversarial verifier attacks the proof using specific failure patterns, not generic 'check logic'. Outputs calibrated confidence — will say 'no confident solution' rather than bluff. If LaTeX is available, produces a clean PDF after verification passes.

### [`siege`](./siege/SKILL.md)

- **Skill Identifier:** `siege`
- **Path:** [`specialized-domains/siege/`](./siege/)
- **Allowed Tools:** `Read, Write, Edit, Glob, Grep, Agent, Bash(python3 ${CLAUDE_SKILL_DIR}/scripts/ledger.py *), Bash(python3 ${CLAUDE_PLUGIN_ROOT}/skills/siege/scripts/ledger.py *), Bash(python ${CLAUDE_SKILL_DIR}/scripts/ledger.py *), Bash(python ${CLAUDE_PLUGIN_ROOT}/skills/siege/scripts/ledger.py *), Bash(mkdir *), Bash(cp *), Bash(mv *), Bash(cat *), Bash(test *), Bash(ls *), Bash(wc *), Bash(cmp *), Bash(grep *), Bash(printf *), Bash(echo *)`
- **Operational Summary:**
  Work on one hard mathematics problem in rounds: each round a judge writes a few self-contained questions, independent workers answer them, and the judge keeps a ledger of what is proved, refuted and open, until the judge concludes or the rounds run out, and then a proof.md says plainly what is and is not proved. A run takes hours and dozens of worker runs. Usage: /math-proof:siege [NAME=value settings] <the problem, stated in full, or the path of a file holding it>.

### [`solo`](./solo/SKILL.md)

- **Skill Identifier:** `solo`
- **Path:** [`specialized-domains/solo/`](./solo/)
- **Allowed Tools:** `Read, Write, Edit, Glob, Grep, Bash(mkdir *), Bash(cp *), Bash(cmp *)`
- **Operational Summary:**
  Work on one hard mathematics problem in this session yourself, with no sub-agents: reason in stages, record each settled step in a notes file so that nothing written is lost if a response is cut off, and end with a self-contained proof.md. Usage: /math-proof:solo <the problem, stated in full, or the path of a file holding it>.

---

## Usage & Integration

To integrate these skills into an agent workspace or CLI:

```bash
# Symlink an individual skill into your agent skills path
ln -s ~/skills/specialized-domains/<skill-name> ~/.gemini/skills/<skill-name>

# Or copy into Claude Code project skills
cp -r ~/skills/specialized-domains/<skill-name> .claude/skills/
```

---

## Attribution & Curatorial Notice

The skills in this category were curated, structured, and dereferenced by Youssef Fellah ([ind4x_](https://github.com/ind4x)) from official repositories, platform plugins, and community tools. Original copyrights and intellectual property belong to their respective authors.
