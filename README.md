# EventsourceEx

An Elixir EventSource (Server-Sent Events) client

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add eventsource_ex to your list of dependencies in `mix.exs`:

        def deps do
          [{:eventsource_ex, "~> 0.0.1"}]
        end

  2. Ensure eventsource_ex is started before your application:

        def application do
          [applications: [:eventsource_ex]]
        end

## Usage

    iex(1)> {:ok, pid} = EventsourceEx.new("https://url.com/stream", stream_to: self)
    {:ok, #PID<0.150.0>}
    iex(2)> flush
    %EventsourceEx.Message{data: "1", event: "message", id: nil}
    %EventsourceEx.Message{data: "2", event: "message", id: nil}
    %EventsourceEx.Message{data: "3", event: "message", id: nil}
    :ok
