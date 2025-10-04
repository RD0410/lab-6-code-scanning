# Answers to Part 3

Add your answers to the questions in Part 3, Step 2 below. 

## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
PyYAML (`pkg:pypi/pyyaml@5.1`)

2. Which CVE is linked to this vulnerability?
CVE-2020-14343 — Improper Input Validation

3. What remediation steps do you suggest?
Vulnerability CVE-2020-14343 affects PyYAML <5.4 when untrusted YAML is parsed with the Unsafe loaders,e.g.full_load/FullLoader that can construct arbitrary Python objects, leading to remote code execution.
we can remediate this by upgrading PyYAML to ≥ 5.4 and switching any yaml.load(...) calls to yaml.safe_load(...)  for all untrusted input.

### Vulnerability 2:
1. Which vulnerability are you addressing?
Pillow (installed 9.4.0; affected <=10.1.0)

2. Which CVE is linked to this vulnerability?
CVE-2023-50447 — PIL.ImageMath.eval

3. What remediation steps do you suggest? 
Vulnerability CVE-2023-50447 in Pillow (<=10.1.0) allows arbitrary code execution via PIL.ImageMath.eval when the environment parameter is attacker-controlled.
we remediate this by upgrading Pillow to 10.2.0 or newer and avoiding ImageMath.eval with untrusted input.