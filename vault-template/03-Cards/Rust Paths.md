---
up:
  - "[[Rust]]"
tags:
  - programming
aliases:
  - rust path
date: 2023-11-18
---
# Rust Paths

In [[Rust]], the elements of a [[Rust Crate|Crate]] ([[functions]], [[Rust Modules|modules]], [[structs]], [[enums]], etc.) are organized in a module tree. The visibility of these elements is controlled by the `pub` keyword. Paths allow access to these elements and can be absolute or relative.

## Example of module hierarchy
```
restaurant crate (root)
 └── front_of_house (father module).
     ├── hosting (sub module brother of serving)
     │ ├─── add_to_waitlist (method).
     │ └─── seat_at_table (method).
     └─── serving (sub module brother of hosting).
         ├── take_order (method).
         ├─── serve_order (method).
         └─── take_payment (method).
```


## Visibility rules

- **Default Private**: Items are private unless specified with `pub`.
- **Sister Modules**: Public elements of sister modules are accessible to each other.

## Paths

- **Absolute**: Start from the root of the crate with `crate`, such as `crate::front_of_house::hosting::seat_at_table`.
- **Relative**: Use `self` for the same module or `super` for the parent module. For example, from `hosting`, `super::serving::take_order` accesses `take_order` in `serving`.

## Practical example
```
// In src/front_of_house/hosting.rs

pub fn seat_at_table() {
	// 'self' is optional here
    self::add_to_waitlist();  
    
	// 'super' accesses the parent module 'front_of_house'.
	super::serving::take_order();  
}

```

==**Remember**: `self` is optional when accessing elements within the same module and is necessary for disambiguation or within macros.==








