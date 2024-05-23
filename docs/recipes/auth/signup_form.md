```python exec
import reflex as rx
```

# Sign up Form

The sign up form is a common component in web applications. It allows users to create an account and access the application's features. This page provides a few examples of sign up forms that you can use in your application.

## Default sign up card

```python exec
def signup_default() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.center(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2", text_align="center", width="100%"),
				direction="column",
				spacing="5",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(placeholder="Enter your password", type="password", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.box(
				rx.checkbox(
					"Agree to Terms and Conditions",
					default_checked=True,
					spacing="2"
				),
				width="100%"
			),
			rx.button("Sign in", size="3", width="100%"),
			rx.center(
				rx.text("Already registered?", size="3"),
				rx.link("Sign in", href="#", size="3"),
				opacity="0.8",
				spacing="2",
				direction="row"
			),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

```python demo box
signup_default()
```

```python
def signup_default() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.center(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2", text_align="center", width="100%"),
				direction="column",
				spacing="5",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium"),
				rx.input(placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium"),
				rx.input(placeholder="Enter your password", type="password", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.checkbox(
                "Agree to Terms and Conditions",
                default_checked=True,
                spacing="2"
            ),
			rx.button("Sign in", size="3", width="100%"),
			rx.center(
				rx.text("Already registered?", size="3"),
				rx.link("Sign in", href="#", size="3"),
				opacity="0.8",
				spacing="2",
				direction="row",
				width="100%"
			),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

## Default sign up card with icons

```python exec
def signup_default_icons() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.center(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2", text_align="center", width="100%"),
				direction="column",
				spacing="5",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.box(
				rx.checkbox(
					"Agree to Terms and Conditions",
					default_checked=True,
					spacing="2"
				),
				width="100%"
			),
			rx.button("Sign in", size="3", width="100%"),
			rx.center(
				rx.text("Already registered?", size="3"),
				rx.link("Sign in", href="#", size="3"),
				opacity="0.8",
				spacing="2",
				direction="row",
				width="100%"
			),
			spacing="6",
			width="100%"
		),
		max_width="28em",
		size="4",
		width="100%"
	)
```

```python demo box
signup_default_icons()
```

```python
def signup_default_icons() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.center(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2"),
				direction="column",
				spacing="5",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium"),
				rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium"),
				rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.checkbox(
                "Agree to Terms and Conditions",
                default_checked=True,
                spacing="2"
            ),
			rx.button("Sign in", size="3", width="100%"),
			rx.center(
				rx.text("Already registered?", size="3"),
				rx.link("Sign in", href="#", size="3"),
				opacity="0.8",
				spacing="2",
				direction="row",
				width="100%"
			),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

## Sign up card with third-party auth provider

```python exec
def signup_single_thirdparty() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.flex(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2", text_align="left", width="100%"),
				rx.hstack(
					rx.text("Already registered?", size="3", text_align="left"),
					rx.link("Sign in", href="#", size="3"),
					spacing="2",
					opacity="0.8",
					width="100%"
				),
				direction="column",
				justify="start",
				spacing="4",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.box(
				rx.checkbox(
					"Agree to Terms and Conditions",
					default_checked=True,
					spacing="2"
				),
				width="100%"
			),
			rx.button("Sign in", size="3", width="100%"),
			rx.hstack(
				rx.divider(margin="0"),
				rx.text("Or continue with", white_space="nowrap", weight="medium"),
				rx.divider(margin="0"),
				align="center",
				width="100%"
			),
			rx.button(
				rx.icon(tag="github"),
				"Sign in with Github",
				variant="outline",
				size="3",
				width="100%"
			),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

```python demo box
signup_single_thirdparty()
```

```python
def signup_single_thirdparty() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.vstack(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2"),
				rx.hstack(
					rx.text("Already registered?", size="3"),
					rx.link("Sign in", href="#", size="3"),
					spacing="2",
					opacity="0.8",
					width="100%"
				),
				spacing="4",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium"),
				rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium"),
				rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
				spacing="2",
				width="100%"
			),
			rx.checkbox(
				"Agree to Terms and Conditions",
				default_checked=True,
				spacing="2"
			),
			rx.button("Sign in", size="3", width="100%"),
			rx.hstack(
				rx.divider(),
				rx.text("Or continue with", white_space="nowrap", weight="medium"),
				rx.divider(),
				align="center",
				width="100%"
			),
			rx.button(
				rx.icon(tag="github"),
				"Sign in with Github",
				size="3",
				variant="outline",
				width="100%"
			),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

## Sign up card with multiple third-party auth providers

```python exec
def signup_multiple_thirdparty() -> rx.Component:
	return rx.card(
		rx.vstack(
			rx.flex(
				rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
				rx.heading("Create an account", size="6", as_="h2", width="100%"),
				rx.hstack(
					rx.text("Already registered?", size="3", text_align="left"),
					rx.link("Sign in", href="#", size="3"),
					spacing="2",
					opacity="0.8",
					width="100%"
				),
				justify="start",
				direction="column",
				spacing="4",
				width="100%"
			),
			rx.vstack(
				rx.text("Email address", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.vstack(
				rx.text("Password", size="3", weight="medium", text_align="left", width="100%"),
				rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
				justify="start",
				spacing="2",
				width="100%"
			),
			rx.box(
				rx.checkbox(
					"Agree to Terms and Conditions",
					default_checked=True,
					spacing="2"
				),
				width="100%"
			),
			rx.button("Sign in", size="3", width="100%"),
			rx.hstack(
				rx.divider(margin="0"),
				rx.text("Or continue with", white_space="nowrap", weight="medium"),
				rx.divider(margin="0"),
				align="center",
				width="100%"
			),
			rx.center(
                rx.icon_button(
                    rx.icon(tag="github"),
                    variant="soft",
                    size="3"
                ),
                rx.icon_button(
                    rx.icon(tag="facebook"),
                    variant="soft",
                    size="3"
                ),
                rx.icon_button(
                    rx.icon(tag="twitter"),
                    variant="soft",
                    size="3"
                ),
                spacing="4",
                direction="row",
                width="100%"
            ),
			spacing="6",
			width="100%"
		),
		size="4",
		max_width="28em",
		width="100%"
	)
```

```python demo box
signup_multiple_thirdparty()
```

```python
def signup_multiple_thirdparty() -> rx.Component:
    return rx.card(
        rx.vstack(
            rx.vstack(
                rx.image(src="/favicon.ico", width="2.5em", height="auto", border_radius="50%"),
                rx.heading("Create an account", size="6", as_="h2"),
                rx.hstack(
                    rx.text("Already registered?", size="3"),
                    rx.link("Sign in", href="#", size="3"),
                    spacing="2",
                    opacity="0.8",
                    width="100%"
                ),
                spacing="4",
                width="100%"
            ),
            rx.vstack(
                rx.text("Email address", size="3", weight="medium"),
                rx.input(rx.input.slot(rx.icon("user")), placeholder="user@reflex.dev", type="email", size="3", width="100%"),
                spacing="2",
                width="100%"
            ),
            rx.vstack(
                rx.text("Password", size="3", weight="medium"),
                rx.input(rx.input.slot(rx.icon("lock")), placeholder="Enter your password", type="password", size="3", width="100%"),
                spacing="2",
                width="100%"
            ),
			rx.box(
				rx.checkbox(
					"Agree to Terms and Conditions",
					default_checked=True,
					spacing="2"
				),
				width="100%"
			),
            rx.button("Sign in", size="3", width="100%"),
            rx.hstack(
                rx.divider(),
                rx.text("Or continue with", white_space="nowrap", weight="medium"),
                rx.divider(),
                align="center",
                width="100%"
            ),
            rx.center(
                rx.icon_button(
                    rx.icon(tag="github"),
                    variant="soft",
                    size="3",
                ),
                rx.icon_button(
                    rx.icon(tag="facebook"),
                    variant="soft",
                    size="3",
                ),
                rx.icon_button(
                    rx.icon(tag="twitter"),
                    variant="soft",
                    size="3",
                ),
                spacing="4",
                direction="row",
                width="100%"
            ),
            spacing="6",
            width="100%"
        ),
        max_width="28em",
        size="4",
        width="100%"
    )
```