# VHDL

## Structure

VHDL model consist of 2 parts *Entity* and *Architecture*

The *Entity* defines interface, the *Architecture* defines function

Entity declaration format:

```vhdl
entity entity_name is
  [generic (generic_list);]
  [port (port_list);]
end entity_name;
```

For example:

```vhdl
entity singed_adder is
  port (
    aclr : in std_logic;
    clk  : in std_logic;
    a    : in std_logic_vector;
    b    : in std_logic_vector;
    q    : out std_logic_vector;
  )
end signed_adder;
```

### Port statement

Entities ```port``` statement identifies the port used by entity to communitcate with its environment

Port statement format:

```vhdl
port (
  name_list : mode type;
  name_list : mode type;
  name_list : mode type;
  name_list : mode type;
)
```

Use one line per signal

### Architecture body

Architecture body describes the operation of the component

Format:

```vhdl
architecture body_name of entity_name is
  -- this is the ->declaractive area<-
  -- declare signals, variables, components, subprograms
  begin
    -- this is the ->statement area<-
    -- this is the "execution part" of the model
end body_name
```

The ```entity_name``` in the architecture statement must be the same as the entity declaration

```vhdl
entity entity_name is

architecture body_name of entity_name is
```

The ```body_name``` is a user-defined name that should uniquely describe the particular architecture model

```vhdl
architecture beh of nand_gate is
architecture struct of nand_gate is
```

NOTE: mutiple architectures are allowed.
