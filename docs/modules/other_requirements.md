# Other Requirements and Issues

## Module Dependencies Issues

### Circular Dependencies Problem
Dependencies between the custom modules are inconsistent, must be fixed and custom code must be placed in the correct place.

**Example**: 
- `yuhelia_base` module depends on `pick_pack_ship`
- `pick_pack_ship` module depends on `yuhelia_base`
- This causes inconsistency and trouble when upgrading

### Required Actions
- Audit all custom module dependencies
- Identify circular dependency chains
- Move shared code to appropriate base modules
- Fix dependencies to ensure proper hierarchy
- Test module upgrades independently