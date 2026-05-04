---
name: realtime
description: "LiveKit Python SDK for real-time video, audio, and data communication including room management and recording."
metadata:
  languages: "python"
  versions: "1.0.17"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "livekit,python,realtime,webrtc,video,audio,AVSynchronizer,aclose,clear_queue,push,reset,wait_for_playout,AudioFilter,AudioFrame,create,to_wav_bytes,AudioFrameEvent,AudioMixer,add_stream,end_input,remove_stream,AudioProcessingModule,process_reverse_stream,process_stream,set_stream_delay_ms,AudioResampler,flush,AudioResamplerQuality,AudioSource,capture_frame,AudioStream,from_participant,from_track,ByteStreamInfo,ByteStreamReader,ByteStreamWriter,write,ConnectError,DataPacket,DataTrackFrame,DataTrackInfo,DataTrackStream,close,read,E2EEManager,frame_cryptors,set_enabled,E2EEOptions,EventEmitter,emit,off,on,once,FrameCryptor,set_key_index,FrameProcessor,KeyProvider,export_key,export_shared_key,ratchet_key,ratchet_shared_key,set_key,set_shared_key,KeyProviderOptions,LocalAudioTrack,create_audio_track,get_stats,mute,unmute,LocalDataTrack,is_published,try_push,unpublish,LocalParticipant,perform_rpc,publish_data,publish_data_track,publish_dtmf,publish_track,publish_transcription,register_rpc_method,send_file,send_text,set_attributes,set_metadata,set_name,set_track_subscription_permissions,stream_bytes,stream_text,unpublish_track,unregister_rpc_method,LocalTrackPublication,wait_for_subscription,LocalVideoTrack,create_video_track,MediaDevices,default_input_device,default_output_device,list_input_devices,list_output_devices,open_input,open_output,NoiseCancellationOptions,Participant,PushFrameError,RemoteAudioTrack,RemoteDataTrack,subscribe,RemoteParticipant,RemoteTrackPublication,set_subscribed,RemoteVideoTrack,Room,connect,disconnect,get_rtc_stats,isconnected,register_byte_stream_handler,register_text_stream_handler,unregister_byte_stream_handler,unregister_text_stream_handler,RoomOptions,RpcError,RpcInvocationData,RtcConfiguration,RtcStats,SipDTMF,SubscribeDataTrackError,TextStreamInfo,TextStreamReader,read_all,TextStreamWriter,Track,TrackPublication,Transcription,TranscriptionSegment,VideoFrame,convert,get_plane,VideoFrameEvent,VideoSource,VideoStream,combine_audio_frames,FfiClient,request,FfiHandle,dispose,get_address"
---

# livekit — realtime

## Install

```bash
pip install livekit
```

## Imports

```python
import livekit
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AVSynchronizer` | Class | Synchronize audio and video capture.  Usage:     av_sync = AVSynchronizer(… |
| `aclose` | Method |  |
| `clear_queue` | Method |  |
| `push` | Method | Push a frame to the synchronizer  Args:     frame: The video or audio frame to… |
| `reset` | Method |  |
| `wait_for_playout` | Method | Wait until all video and audio frames are played out. |
| `AudioFilter` | Class |  |
| `AudioFrame` | Class | A class that represents a frame of audio data with specific properties such as… |
| `create` | Method | Create a new empty AudioFrame instance with specified sample rate, number of ch… |
| `to_wav_bytes` | Method | Convert the audio frame data to a WAV-formatted byte stream.  Returns:     byte… |
| `AudioFrameEvent` | Class | An event representing a received audio frame.  Attributes:     frame (AudioFram… |
| `AudioMixer` | Class |  |
| `aclose` | Method | Immediately stop mixing and close the mixer.  This cancels the mixing task, and… |
| `add_stream` | Method | Add an audio stream to the mixer.  The stream is added to the internal set of s… |
| `end_input` | Method | Signal that no more streams will be added.  This method marks the mixer as clos… |
| `remove_stream` | Method | Remove an audio stream from the mixer.  This method removes the specified strea… |
| `AudioProcessingModule` | Class | Provides WebRTC audio processing capabilities including echo cancellation, nois… |
| `process_reverse_stream` | Method | Process the reverse audio frame (typically used for echo cancellation in a full… |
| `process_stream` | Method | Process the provided audio frame using the configured audio processing features… |
| `set_stream_delay_ms` | Method | This must be called if and only if echo processing is enabled.  Sets the `delay… |
| `AudioResampler` | Class | A class for resampling audio data from one sample rate to another.  `AudioResam… |
| `flush` | Method | Flush any remaining audio data through the resampler and retrieve the resampled… |
| `push` | Method | Push audio data into the resampler and retrieve any available resampled data.… |
| `AudioResamplerQuality` | Class | str(object='') -> str str(bytes_or_buffer[, encoding[, errors]]) -> str  Create… |
| `AudioSource` | Class | Represents a real-time audio source with an internal audio queue.  The `AudioSo… |
| `aclose` | Method | Close the audio source  This method cleans up resources associated with the aud… |
| `capture_frame` | Method | Captures an `AudioFrame` and queues it for playback.  This method is used to pu… |
| `clear_queue` | Method | Clears the internal audio queue, discarding all buffered audio data.  This meth… |
| `wait_for_playout` | Method | Waits for the audio source to finish playing out all audio data.  This method e… |
| `AudioStream` | Class | An asynchronous audio stream for receiving audio frames from a participant or t… |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `AVSynchronizer`

Synchronize audio and video capture.

Usage:
    av_sync = AVSynchronizer(
        audio_source=audio_source,
        video_source=video_source,
        video_fps=video_fps,
    )

    async for vide…

```python
livekit.rtc.AVSynchronizer(self, *, audio_source: livekit.rtc.audio_source.AudioSource, video_source: livekit.rtc.video_source.VideoSource, video_fps: float, video_queue_size_ms: float = 100, _max_delay_tolerance_ms: float = 300)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `audio_source` | `AudioSource` | `—` | kw |
| `video_source` | `VideoSource` | `—` | kw |
| `video_fps` | `float` | `—` | kw |
| `video_queue_size_ms` | `float` | `100` | kw |
| `_max_delay_tolerance_ms` | `float` | `300` | kw |

### `AudioFilter`

```python
livekit.rtc.AudioFilter(self, module_id: str, path: str, dependencies: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module_id` | `str` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `dependencies` | `Optional` | `None` | pos/kw |

### `AudioFrame`

A class that represents a frame of audio data with specific properties such as sample rate,
number of channels, and samples per channel.

The format of the audio data is 16-bit signed integers (int16…

```python
livekit.rtc.AudioFrame(self, data: Union[bytes, bytearray, memoryview], sample_rate: int, num_channels: int, samples_per_channel: int, *, userdata: Optional[dict[str, Any]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |
| `userdata` | `Optional` | `None` | kw |

### `AudioFrameEvent`

An event representing a received audio frame.

Attributes:
    frame (AudioFrame): The received audio frame.

```python
livekit.rtc.AudioFrameEvent(self, frame: 'AudioFrame') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `frame` | `AudioFrame` | `—` | pos/kw |

### `AudioMixer`

```python
livekit.rtc.AudioMixer(self, sample_rate: int, num_channels: int, *, blocksize: int = 0, stream_timeout_ms: int = 100, capacity: int = 100) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `blocksize` | `int` | `0` | kw |
| `stream_timeout_ms` | `int` | `100` | kw |
| `capacity` | `int` | `100` | kw |

### `AudioProcessingModule`

Provides WebRTC audio processing capabilities including echo cancellation, noise suppression,
high-pass filtering, and gain control.

```python
livekit.rtc.AudioProcessingModule(self, *, echo_cancellation: 'bool' = False, noise_suppression: 'bool' = False, high_pass_filter: 'bool' = False, auto_gain_control: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `echo_cancellation` | `bool` | `False` | kw |
| `noise_suppression` | `bool` | `False` | kw |
| `high_pass_filter` | `bool` | `False` | kw |
| `auto_gain_control` | `bool` | `False` | kw |

### `AudioResampler`

A class for resampling audio data from one sample rate to another.

`AudioResampler` provides functionality to resample audio data from an input sample rate to an output
sample rate using the Sox res…

```python
livekit.rtc.AudioResampler(self, input_rate: 'int', output_rate: 'int', *, num_channels: 'int' = 1, quality: 'AudioResamplerQuality' = <AudioResamplerQuality.MEDIUM: 'medium'>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_rate` | `int` | `—` | pos/kw |
| `output_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `1` | kw |
| `quality` | `AudioResamplerQuality` | `<AudioResamplerQuality.MEDIUM: 'medium'>` | kw |

### `AudioResamplerQuality`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
livekit.rtc.AudioResamplerQuality(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `AudioSource`

Represents a real-time audio source with an internal audio queue.

The `AudioSource` class allows you to push audio frames into a real-time audio
source, managing an internal queue of audio data up t…

```python
livekit.rtc.AudioSource(self, sample_rate: 'int', num_channels: 'int', queue_size_ms: 'int' = 1000, loop: 'asyncio.AbstractEventLoop | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `queue_size_ms` | `int` | `1000` | pos/kw |
| `loop` | `asyncio.AbstractEventLoop \| None` | `None` | pos/kw |

### `AudioStream`

An asynchronous audio stream for receiving audio frames from a participant or track.

The `AudioStream` class provides an asynchronous iterator over audio frames received from
a specific track or par…

```python
livekit.rtc.AudioStream(self, track: 'Track', loop: 'Optional[asyncio.AbstractEventLoop]' = None, capacity: 'int' = 0, sample_rate: 'int' = 48000, num_channels: 'int' = 1, frame_size_ms: 'int | None' = None, noise_cancellation: 'Optional[NoiseCancellationOptions | FrameProcessor[AudioFrame]]' = None, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `track` | `Track` | `—` | pos/kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | pos/kw |
| `capacity` | `int` | `0` | pos/kw |
| `sample_rate` | `int` | `48000` | pos/kw |
| `num_channels` | `int` | `1` | pos/kw |
| `frame_size_ms` | `int \| None` | `None` | pos/kw |
| `noise_cancellation` | `Optional[NoiseCancellationOptions \| FrameProcessor[AudioFrame]]` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ByteStreamInfo`

ByteStreamInfo(stream_id: 'str', mime_type: 'str', topic: 'str', timestamp: 'int', size: 'Optional[int]', attributes: 'Optional[Dict[str, str]]', name: 'str')

```python
livekit.rtc.ByteStreamInfo(self, stream_id: 'str', mime_type: 'str', topic: 'str', timestamp: 'int', size: 'Optional[int]', attributes: 'Optional[Dict[str, str]]', name: 'str') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stream_id` | `str` | `—` | pos/kw |
| `mime_type` | `str` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |
| `timestamp` | `int` | `—` | pos/kw |
| `size` | `Optional[int]` | `—` | pos/kw |
| `attributes` | `Optional[Dict[str, str]]` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `ByteStreamReader`

```python
livekit.rtc.ByteStreamReader(self, header: 'proto_DataStream.Header', capacity: 'int' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `header` | `proto_DataStream.Header` | `—` | pos/kw |
| `capacity` | `int` | `0` | pos/kw |

### `ByteStreamWriter`

```python
livekit.rtc.ByteStreamWriter(self, local_participant: 'LocalParticipant', *, name: 'str', topic: 'str' = '', attributes: 'Optional[Dict[str, str]]' = None, stream_id: 'str | None' = None, total_size: 'int | None' = None, mime_type: 'str' = 'application/octet-stream', destination_identities: 'Optional[List[str]]' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `local_participant` | `LocalParticipant` | `—` | pos/kw |
| `name` | `str` | `—` | kw |
| `topic` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |
| `stream_id` | `str \| None` | `None` | kw |
| `total_size` | `int \| None` | `None` | kw |
| `mime_type` | `str` | `'application/octet-stream'` | kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |

### `ConnectError`

Common base class for all non-exit exceptions.

```python
livekit.rtc.ConnectError(self, message: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `DataPacket`

DataPacket(data: 'bytes', kind: 'proto_room.DataPacketKind.ValueType', participant: 'RemoteParticipant | None', topic: 'str | None' = None)

```python
livekit.rtc.DataPacket(self, data: 'bytes', kind: 'proto_room.DataPacketKind.ValueType', participant: 'RemoteParticipant | None', topic: 'str | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `bytes` | `—` | pos/kw |
| `kind` | `proto_room.DataPacketKind.ValueType` | `—` | pos/kw |
| `participant` | `RemoteParticipant \| None` | `—` | pos/kw |
| `topic` | `str \| None` | `None` | pos/kw |

### `DataTrackFrame`

A frame published on a data track, consisting of a payload and optional metadata.

```python
livekit.rtc.DataTrackFrame(self, payload: 'bytes', user_timestamp: 'Optional[int]' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |
| `user_timestamp` | `Optional[int]` | `None` | pos/kw |

### `DataTrackInfo`

Information about a published data track.

```python
livekit.rtc.DataTrackInfo(self, sid: 'str', name: 'str', uses_e2ee: 'bool') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sid` | `str` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `uses_e2ee` | `bool` | `—` | pos/kw |

### `DataTrackStream`

An active subscription to a remote data track.

Use as an async iterator to receive frames::

    stream = remote_track.subscribe()
    async for frame in stream:
        process(frame.payload)

Drop…

```python
livekit.rtc.DataTrackStream(self, owned_info: 'proto_data_track.OwnedDataTrackStream') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `proto_data_track.OwnedDataTrackStream` | `—` | pos/kw |

### `E2EEManager`

```python
livekit.rtc.E2EEManager(self, room_handle: int, options: Optional[livekit.rtc.e2ee.E2EEOptions])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `room_handle` | `int` | `—` | pos/kw |
| `options` | `Optional` | `—` | pos/kw |

### `E2EEOptions`

E2EEOptions(key_provider_options: livekit.rtc.e2ee.KeyProviderOptions = <factory>, encryption_type: int = 1)

```python
livekit.rtc.E2EEOptions(self, key_provider_options: livekit.rtc.e2ee.KeyProviderOptions = <factory>, encryption_type: int = 1) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key_provider_options` | `KeyProviderOptions` | `<factory>` | pos/kw |
| `encryption_type` | `int` | `1` | pos/kw |

### `EventEmitter`

Abstract base class for generic types.

On Python 3.12 and newer, generic classes implicitly inherit from
Generic when they declare a parameter list after the class's name::

    class Mapping[KT, VT…

```python
livekit.rtc.EventEmitter(self) -> None
```

### `FrameCryptor`

```python
livekit.rtc.FrameCryptor(self, room_handle: int, participant_identity: str, key_index: int, enabled: bool)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `room_handle` | `int` | `—` | pos/kw |
| `participant_identity` | `str` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |
| `enabled` | `bool` | `—` | pos/kw |

### `FrameProcessor`

Abstract base class for generic types.

On Python 3.12 and newer, generic classes implicitly inherit from
Generic when they declare a parameter list after the class's name::

    class Mapping[KT, VT…

```python
livekit.rtc.FrameProcessor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `KeyProvider`

```python
livekit.rtc.KeyProvider(self, room_handle: int, options: livekit.rtc.e2ee.KeyProviderOptions)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `room_handle` | `int` | `—` | pos/kw |
| `options` | `KeyProviderOptions` | `—` | pos/kw |

### `KeyProviderOptions`

KeyProviderOptions(shared_key: Optional[bytes] = None, ratchet_salt: bytes = b'LKFrameEncryptionKey', ratchet_window_size: int = 16, failure_tolerance: int = -1, key_ring_size: int = 16, key_derivati…

```python
livekit.rtc.KeyProviderOptions(self, shared_key: Optional[bytes] = None, ratchet_salt: bytes = b'LKFrameEncryptionKey', ratchet_window_size: int = 16, failure_tolerance: int = -1, key_ring_size: int = 16, key_derivation_function: int = 0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `shared_key` | `Optional` | `None` | pos/kw |
| `ratchet_salt` | `bytes` | `b'LKFrameEncryptionKey'` | pos/kw |
| `ratchet_window_size` | `int` | `16` | pos/kw |
| `failure_tolerance` | `int` | `-1` | pos/kw |
| `key_ring_size` | `int` | `16` | pos/kw |
| `key_derivation_function` | `int` | `0` | pos/kw |

### `LocalAudioTrack`

```python
livekit.rtc.LocalAudioTrack(self, info: track_pb2.OwnedTrack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `OwnedTrack` | `—` | pos/kw |

### `LocalDataTrack`

Data track published by the local participant.

```python
livekit.rtc.LocalDataTrack(self, owned_info: 'proto_data_track.OwnedLocalDataTrack') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `proto_data_track.OwnedLocalDataTrack` | `—` | pos/kw |

### `LocalParticipant`

Represents the local participant in a room.

```python
livekit.rtc.LocalParticipant(self, room_queue: 'BroadcastQueue[proto_ffi.FfiEvent]', owned_info: 'proto_participant.OwnedParticipant') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `room_queue` | `BroadcastQueue[proto_ffi.FfiEvent]` | `—` | pos/kw |
| `owned_info` | `proto_participant.OwnedParticipant` | `—` | pos/kw |

### `LocalTrackPublication`

```python
livekit.rtc.LocalTrackPublication(self, owned_info: track_pb2.OwnedTrackPublication)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `OwnedTrackPublication` | `—` | pos/kw |

### `LocalVideoTrack`

```python
livekit.rtc.LocalVideoTrack(self, info: track_pb2.OwnedTrack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `OwnedTrack` | `—` | pos/kw |

### `MediaDevices`

High-level interface to native audio devices.

- Device enumeration helpers.
- Audio input capture into `rtc.AudioSource` with optional APM processing.
- Audio output player that can feed APM reverse…

```python
livekit.rtc.MediaDevices(self, *, loop: 'Optional[asyncio.AbstractEventLoop]' = None, input_sample_rate: 'int' = 48000, output_sample_rate: 'int' = 48000, num_channels: 'int' = 1, blocksize: 'int' = 4800) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | kw |
| `input_sample_rate` | `int` | `48000` | kw |
| `output_sample_rate` | `int` | `48000` | kw |
| `num_channels` | `int` | `1` | kw |
| `blocksize` | `int` | `4800` | kw |

### `NoiseCancellationOptions`

NoiseCancellationOptions(module_id: 'str', options: 'dict[str, Any]')

```python
livekit.rtc.NoiseCancellationOptions(self, module_id: 'str', options: 'dict[str, Any]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module_id` | `str` | `—` | pos/kw |
| `options` | `dict[str, Any]` | `—` | pos/kw |

### `Participant`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
livekit.rtc.Participant(self, owned_info: 'proto_participant.OwnedParticipant') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `proto_participant.OwnedParticipant` | `—` | pos/kw |

### `PushFrameError`

Frame could not be pushed to a data track.

Pushing a frame can fail for several reasons:

- The track has been unpublished by the local participant or SFU
- The room is no longer connected
- Frames…

```python
livekit.rtc.PushFrameError(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `RemoteAudioTrack`

```python
livekit.rtc.RemoteAudioTrack(self, info: track_pb2.OwnedTrack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `OwnedTrack` | `—` | pos/kw |

### `RemoteDataTrack`

Data track published by a remote participant.

```python
livekit.rtc.RemoteDataTrack(self, owned_info: 'proto_data_track.OwnedRemoteDataTrack') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `proto_data_track.OwnedRemoteDataTrack` | `—` | pos/kw |

### `RemoteParticipant`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
livekit.rtc.RemoteParticipant(self, owned_info: 'proto_participant.OwnedParticipant') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `proto_participant.OwnedParticipant` | `—` | pos/kw |

### `RemoteTrackPublication`

```python
livekit.rtc.RemoteTrackPublication(self, owned_info: track_pb2.OwnedTrackPublication)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `OwnedTrackPublication` | `—` | pos/kw |

### `RemoteVideoTrack`

```python
livekit.rtc.RemoteVideoTrack(self, info: track_pb2.OwnedTrack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `OwnedTrack` | `—` | pos/kw |

### `Room`

Abstract base class for generic types.

On Python 3.12 and newer, generic classes implicitly inherit from
Generic when they declare a parameter list after the class's name::

    class Mapping[KT, VT…

```python
livekit.rtc.Room(self, loop: 'Optional[asyncio.AbstractEventLoop]' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | pos/kw |

### `RoomOptions`

RoomOptions(auto_subscribe: 'bool' = True, dynacast: 'bool' = False, e2ee: 'E2EEOptions | None' = None, encryption: 'E2EEOptions | None' = None, rtc_config: 'RtcConfiguration | None' = None, connect_…

```python
livekit.rtc.RoomOptions(self, auto_subscribe: 'bool' = True, dynacast: 'bool' = False, e2ee: 'E2EEOptions | None' = None, encryption: 'E2EEOptions | None' = None, rtc_config: 'RtcConfiguration | None' = None, connect_timeout: 'float | None' = None, single_peer_connection: 'bool | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auto_subscribe` | `bool` | `True` | pos/kw |
| `dynacast` | `bool` | `False` | pos/kw |
| `e2ee` | `E2EEOptions \| None` | `None` | pos/kw |
| `encryption` | `E2EEOptions \| None` | `None` | pos/kw |
| `rtc_config` | `RtcConfiguration \| None` | `None` | pos/kw |
| `connect_timeout` | `float \| None` | `None` | pos/kw |
| `single_peer_connection` | `bool \| None` | `None` | pos/kw |

### `RpcError`

Specialized error handling for RPC methods.

Instances of this type, when thrown in a method handler, will have their `message`
serialized and sent across the wire. The caller will receive an equival…

```python
livekit.rtc.RpcError(self, code: Union[int, ForwardRef('RpcError.ErrorCode')], message: str, data: Optional[str] = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `Union` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `data` | `Optional` | `None` | pos/kw |

### `RpcInvocationData`

Data passed to method handler for incoming RPC invocations

Attributes:
    request_id (str): The unique request ID. Will match at both sides of the call, useful for debugging or logging.
    caller_…

```python
livekit.rtc.RpcInvocationData(self, request_id: str, caller_identity: str, payload: str, response_timeout: float) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request_id` | `str` | `—` | pos/kw |
| `caller_identity` | `str` | `—` | pos/kw |
| `payload` | `str` | `—` | pos/kw |
| `response_timeout` | `float` | `—` | pos/kw |

### `RtcConfiguration`

RtcConfiguration(ice_transport_type: 'proto_room.IceTransportType.ValueType' = 2, continual_gathering_policy: 'proto_room.ContinualGatheringPolicy.ValueType' = 1, ice_servers: 'list[proto_room.IceSer…

```python
livekit.rtc.RtcConfiguration(self, ice_transport_type: 'proto_room.IceTransportType.ValueType' = 2, continual_gathering_policy: 'proto_room.ContinualGatheringPolicy.ValueType' = 1, ice_servers: 'list[proto_room.IceServer]' = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ice_transport_type` | `proto_room.IceTransportType.ValueType` | `2` | pos/kw |
| `continual_gathering_policy` | `proto_room.ContinualGatheringPolicy.ValueType` | `1` | pos/kw |
| `ice_servers` | `list[proto_room.IceServer]` | `<factory>` | pos/kw |

### `RtcStats`

RtcStats(publisher_stats: 'list[proto_stats.RtcStats]', subscriber_stats: 'list[proto_stats.RtcStats]')

```python
livekit.rtc.RtcStats(self, publisher_stats: 'list[proto_stats.RtcStats]', subscriber_stats: 'list[proto_stats.RtcStats]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `publisher_stats` | `list[proto_stats.RtcStats]` | `—` | pos/kw |
| `subscriber_stats` | `list[proto_stats.RtcStats]` | `—` | pos/kw |

### `SipDTMF`

SipDTMF(code: 'int', digit: 'str', participant: 'RemoteParticipant | None' = None)

```python
livekit.rtc.SipDTMF(self, code: 'int', digit: 'str', participant: 'RemoteParticipant | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `int` | `—` | pos/kw |
| `digit` | `str` | `—` | pos/kw |
| `participant` | `RemoteParticipant \| None` | `None` | pos/kw |

### `SubscribeDataTrackError`

An error that can occur when subscribing to a data track.

```python
livekit.rtc.SubscribeDataTrackError(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `TextStreamInfo`

TextStreamInfo(stream_id: 'str', mime_type: 'str', topic: 'str', timestamp: 'int', size: 'Optional[int]', attributes: 'Optional[Dict[str, str]]', attachments: 'List[str]')

```python
livekit.rtc.TextStreamInfo(self, stream_id: 'str', mime_type: 'str', topic: 'str', timestamp: 'int', size: 'Optional[int]', attributes: 'Optional[Dict[str, str]]', attachments: 'List[str]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stream_id` | `str` | `—` | pos/kw |
| `mime_type` | `str` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |
| `timestamp` | `int` | `—` | pos/kw |
| `size` | `Optional[int]` | `—` | pos/kw |
| `attributes` | `Optional[Dict[str, str]]` | `—` | pos/kw |
| `attachments` | `List[str]` | `—` | pos/kw |

### `TextStreamReader`

```python
livekit.rtc.TextStreamReader(self, header: 'proto_DataStream.Header') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `header` | `proto_DataStream.Header` | `—` | pos/kw |

### `TextStreamWriter`

```python
livekit.rtc.TextStreamWriter(self, local_participant: 'LocalParticipant', *, topic: 'str' = '', attributes: 'Optional[Dict[str, str]]' = {}, stream_id: 'str | None' = None, total_size: 'int | None' = None, reply_to_id: 'str | None' = None, destination_identities: 'Optional[List[str]]' = None, sender_identity: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `local_participant` | `LocalParticipant` | `—` | pos/kw |
| `topic` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `{}` | kw |
| `stream_id` | `str \| None` | `None` | kw |
| `total_size` | `int \| None` | `None` | kw |
| `reply_to_id` | `str \| None` | `None` | kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |
| `sender_identity` | `str \| None` | `None` | kw |

### `Track`

```python
livekit.rtc.Track(self, owned_info: track_pb2.OwnedTrack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `OwnedTrack` | `—` | pos/kw |

### `TrackPublication`

```python
livekit.rtc.TrackPublication(self, owned_info: track_pb2.OwnedTrackPublication)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `owned_info` | `OwnedTrackPublication` | `—` | pos/kw |

### `Transcription`

Transcription(participant_identity: str, track_sid: str, segments: List[ForwardRef('TranscriptionSegment')])

```python
livekit.rtc.Transcription(self, participant_identity: str, track_sid: str, segments: List[ForwardRef('TranscriptionSegment')]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `participant_identity` | `str` | `—` | pos/kw |
| `track_sid` | `str` | `—` | pos/kw |
| `segments` | `List` | `—` | pos/kw |

### `TranscriptionSegment`

TranscriptionSegment(id: str, text: str, start_time: int, end_time: int, language: str, final: bool)

```python
livekit.rtc.TranscriptionSegment(self, id: str, text: str, start_time: int, end_time: int, language: str, final: bool) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `str` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `start_time` | `int` | `—` | pos/kw |
| `end_time` | `int` | `—` | pos/kw |
| `language` | `str` | `—` | pos/kw |
| `final` | `bool` | `—` | pos/kw |

### `VideoFrame`

Represents a video frame with associated metadata and pixel data.

This class provides methods to access video frame properties such as width, height,
and pixel format, as well as methods for manipul…

```python
livekit.rtc.VideoFrame(self, width: int, height: int, type: int, data: Union[bytes, bytearray, memoryview]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `width` | `int` | `—` | pos/kw |
| `height` | `int` | `—` | pos/kw |
| `type` | `int` | `—` | pos/kw |
| `data` | `Union` | `—` | pos/kw |

### `VideoFrameEvent`

VideoFrameEvent(frame: 'VideoFrame', timestamp_us: 'int', rotation: 'proto_video_frame.VideoRotation')

```python
livekit.rtc.VideoFrameEvent(self, frame: 'VideoFrame', timestamp_us: 'int', rotation: 'proto_video_frame.VideoRotation') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `frame` | `VideoFrame` | `—` | pos/kw |
| `timestamp_us` | `int` | `—` | pos/kw |
| `rotation` | `proto_video_frame.VideoRotation` | `—` | pos/kw |

### `VideoSource`

```python
livekit.rtc.VideoSource(self, width: 'int', height: 'int', *, is_screencast: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `width` | `int` | `—` | pos/kw |
| `height` | `int` | `—` | pos/kw |
| `is_screencast` | `bool` | `False` | kw |

### `VideoStream`

VideoStream is a stream of video frames received from a RemoteTrack.

```python
livekit.rtc.VideoStream(self, track: 'Track', loop: 'Optional[asyncio.AbstractEventLoop]' = None, capacity: 'int' = 0, format: 'Optional[proto_video_frame.VideoBufferType.ValueType]' = None, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `track` | `Track` | `—` | pos/kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | pos/kw |
| `capacity` | `int` | `0` | pos/kw |
| `format` | `Optional[proto_video_frame.VideoBufferType.ValueType]` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `AudioFrame`

A class that represents a frame of audio data with specific properties such as sample rate,
number of channels, and samples per channel.

The format of the audio data is 16-bit signed integers (int16…

```python
livekit.rtc.apm.AudioFrame(self, data: Union[bytes, bytearray, memoryview], sample_rate: int, num_channels: int, samples_per_channel: int, *, userdata: Optional[dict[str, Any]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |
| `userdata` | `Optional` | `None` | kw |

### `AudioProcessingModule`

Provides WebRTC audio processing capabilities including echo cancellation, noise suppression,
high-pass filtering, and gain control.

```python
livekit.rtc.apm.AudioProcessingModule(self, *, echo_cancellation: 'bool' = False, noise_suppression: 'bool' = False, high_pass_filter: 'bool' = False, auto_gain_control: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `echo_cancellation` | `bool` | `False` | kw |
| `noise_suppression` | `bool` | `False` | kw |
| `high_pass_filter` | `bool` | `False` | kw |
| `auto_gain_control` | `bool` | `False` | kw |

### `FfiClient`

```python
livekit.rtc.apm.FfiClient(self) -> None
```

### `FfiHandle`

```python
livekit.rtc.apm.FfiHandle(self, handle: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `handle` | `int` | `—` | pos/kw |

### `AudioFilter`

```python
livekit.rtc.audio_filter.AudioFilter(self, module_id: str, path: str, dependencies: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module_id` | `str` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `dependencies` | `Optional` | `None` | pos/kw |

### `FfiClient`

```python
livekit.rtc.audio_filter.FfiClient(self) -> None
```

### `AudioFrame`

A class that represents a frame of audio data with specific properties such as sample rate,
number of channels, and samples per channel.

The format of the audio data is 16-bit signed integers (int16…

```python
livekit.rtc.audio_frame.AudioFrame(self, data: Union[bytes, bytearray, memoryview], sample_rate: int, num_channels: int, samples_per_channel: int, *, userdata: Optional[dict[str, Any]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |
| `userdata` | `Optional` | `None` | kw |

### `FfiHandle`

```python
livekit.rtc.audio_frame.FfiHandle(self, handle: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `handle` | `int` | `—` | pos/kw |

### `AudioFrame`

A class that represents a frame of audio data with specific properties such as sample rate,
number of channels, and samples per channel.

The format of the audio data is 16-bit signed integers (int16…

```python
livekit.rtc.audio_mixer.AudioFrame(self, data: Union[bytes, bytearray, memoryview], sample_rate: int, num_channels: int, samples_per_channel: int, *, userdata: Optional[dict[str, Any]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |
| `userdata` | `Optional` | `None` | kw |

### `AudioMixer`

```python
livekit.rtc.audio_mixer.AudioMixer(self, sample_rate: int, num_channels: int, *, blocksize: int = 0, stream_timeout_ms: int = 100, capacity: int = 100) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `blocksize` | `int` | `0` | kw |
| `stream_timeout_ms` | `int` | `100` | kw |
| `capacity` | `int` | `100` | kw |

### `AudioFrame`

A class that represents a frame of audio data with specific properties such as sample rate,
number of channels, and samples per channel.

The format of the audio data is 16-bit signed integers (int16…

```python
livekit.rtc.audio_resampler.AudioFrame(self, data: Union[bytes, bytearray, memoryview], sample_rate: int, num_channels: int, samples_per_channel: int, *, userdata: Optional[dict[str, Any]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |
| `userdata` | `Optional` | `None` | kw |

### `AudioResampler`

A class for resampling audio data from one sample rate to another.

`AudioResampler` provides functionality to resample audio data from an input sample rate to an output
sample rate using the Sox res…

```python
livekit.rtc.audio_resampler.AudioResampler(self, input_rate: 'int', output_rate: 'int', *, num_channels: 'int' = 1, quality: 'AudioResamplerQuality' = <AudioResamplerQuality.MEDIUM: 'medium'>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_rate` | `int` | `—` | pos/kw |
| `output_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `1` | kw |
| `quality` | `AudioResamplerQuality` | `<AudioResamplerQuality.MEDIUM: 'medium'>` | kw |

### `AudioResamplerQuality`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
livekit.rtc.audio_resampler.AudioResamplerQuality(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

## Functions

### `combine_audio_frames`

Combines one or more `rtc.AudioFrame` objects into a single `rtc.AudioFrame`.

This function concatenates the audio data from multiple frames, ensuring that
all frames have the same sample rate and n…

```python
livekit.rtc.combine_audio_frames(buffer: 'AudioFrame | list[AudioFrame]') -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `buffer` | `AudioFrame \| list[AudioFrame]` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `get_address`

```python
livekit.rtc.apm.get_address(data: Union[bytes, bytearray, memoryview]) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |

**Returns:** `<class 'int'>`

### `get_address`

```python
livekit.rtc.audio_frame.get_address(data: Union[bytes, bytearray, memoryview]) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Union` | `—` | pos/kw |

**Returns:** `<class 'int'>`

## Methods

### `livekit.rtc.AVSynchronizer` methods

### `aclose`

```python
livekit.rtc.AVSynchronizer.aclose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_queue`

```python
livekit.rtc.AVSynchronizer.clear_queue(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `push`

Push a frame to the synchronizer

Args:
    frame: The video or audio frame to push.
    timestamp: (optional) The timestamp of the frame, for logging purposes for now.
        For AudioFrame, it sho…

```python
livekit.rtc.AVSynchronizer.push(self, frame: Union[livekit.rtc.video_frame.VideoFrame, livekit.rtc.audio_frame.AudioFrame], timestamp: Optional[float] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `frame` | `Union` | `—` | pos/kw |
| `timestamp` | `Optional` | `None` | pos/kw |

### `reset`

```python
livekit.rtc.AVSynchronizer.reset(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `wait_for_playout`

Wait until all video and audio frames are played out.

```python
livekit.rtc.AVSynchronizer.wait_for_playout(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.AudioFrame` methods

### `create`

Create a new empty AudioFrame instance with specified sample rate, number of channels,
and samples per channel.

Args:
    sample_rate (int): The sample rate of the audio in Hz.
    num_channels (int…

```python
livekit.rtc.AudioFrame.create(sample_rate: int, num_channels: int, samples_per_channel: int) -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `to_wav_bytes`

Convert the audio frame data to a WAV-formatted byte stream.

Returns:
    bytes: The audio data encoded in WAV format.

```python
livekit.rtc.AudioFrame.to_wav_bytes(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `livekit.rtc.AudioMixer` methods

### `aclose`

Immediately stop mixing and close the mixer.

This cancels the mixing task, and any unconsumed output in the queue may be dropped.

```python
livekit.rtc.AudioMixer.aclose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `add_stream`

Add an audio stream to the mixer.

The stream is added to the internal set of streams and an empty buffer is initialized for it,
if not already present.

Args:
    stream (AsyncIterator[AudioFrame]):…

```python
livekit.rtc.AudioMixer.add_stream(self, stream: AsyncIterator[livekit.rtc.audio_frame.AudioFrame]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `AsyncIterator` | `—` | pos/kw |

### `end_input`

Signal that no more streams will be added.

This method marks the mixer as closed so that it flushes any remaining buffered output before ending.
Note that existing streams will still be processed un…

```python
livekit.rtc.AudioMixer.end_input(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `remove_stream`

Remove an audio stream from the mixer.

This method removes the specified stream and its associated buffer from the mixer.

Args:
    stream (AsyncIterator[AudioFrame]): The audio stream to remove.

```python
livekit.rtc.AudioMixer.remove_stream(self, stream: AsyncIterator[livekit.rtc.audio_frame.AudioFrame]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `AsyncIterator` | `—` | pos/kw |

### `livekit.rtc.AudioProcessingModule` methods

### `process_reverse_stream`

Process the reverse audio frame (typically used for echo cancellation in a full-duplex setup).

In an echo cancellation scenario, this method is used to process the "far-end" audio
prior to mixing or…

```python
livekit.rtc.AudioProcessingModule.process_reverse_stream(self, data: 'AudioFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `AudioFrame` | `—` | pos/kw |

### `process_stream`

Process the provided audio frame using the configured audio processing features.

The input audio frame is modified in-place (if applicable) by the underlying audio
processing module (e.g., echo canc…

```python
livekit.rtc.AudioProcessingModule.process_stream(self, data: 'AudioFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `AudioFrame` | `—` | pos/kw |

### `set_stream_delay_ms`

This must be called if and only if echo processing is enabled.

Sets the `delay` in ms between `process_reverse_stream()` receiving a far-end
frame and `process_stream()` receiving a near-end frame c…

```python
livekit.rtc.AudioProcessingModule.set_stream_delay_ms(self, delay_ms: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `delay_ms` | `int` | `—` | pos/kw |

### `livekit.rtc.AudioResampler` methods

### `flush`

Flush any remaining audio data through the resampler and retrieve the resampled data.

This method should be called when no more input data will be provided to ensure that all internal
buffers are pr…

```python
livekit.rtc.AudioResampler.flush(self) -> 'list[AudioFrame]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[AudioFrame]`

### `push`

Push audio data into the resampler and retrieve any available resampled data.

This method accepts audio data, resamples it according to the configured input and output rates,
and returns any resampl…

```python
livekit.rtc.AudioResampler.push(self, data: 'bytearray | AudioFrame') -> 'list[AudioFrame]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `bytearray \| AudioFrame` | `—` | pos/kw |

**Returns:** `list[AudioFrame]`

### `livekit.rtc.AudioSource` methods

### `aclose`

Close the audio source

This method cleans up resources associated with the audio source.

```python
livekit.rtc.AudioSource.aclose(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `capture_frame`

Captures an `AudioFrame` and queues it for playback.

This method is used to push new audio data into the audio source. The audio data
will be processed and queued. If the size of the audio frame exc…

```python
livekit.rtc.AudioSource.capture_frame(self, frame: 'AudioFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `frame` | `AudioFrame` | `—` | pos/kw |

### `clear_queue`

Clears the internal audio queue, discarding all buffered audio data.

This method immediately removes all audio data currently queued for playback,
effectively resetting the audio source's buffer. An…

```python
livekit.rtc.AudioSource.clear_queue(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `wait_for_playout`

Waits for the audio source to finish playing out all audio data.

This method ensures that all queued audio data has been played out before returning.
It can be used to synchronize events after audio…

```python
livekit.rtc.AudioSource.wait_for_playout(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.AudioStream` methods

### `aclose`

Asynchronously close the audio stream.

This method cleans up resources associated with the audio stream and waits for
any pending operations to complete.

```python
livekit.rtc.AudioStream.aclose(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_participant`

Create an `AudioStream` from a participant's audio track.

Args:
    participant (Participant): The participant from whom to receive audio.
    track_source (TrackSource.ValueType): The source of the…

```python
livekit.rtc.AudioStream.from_participant(*, participant: 'Participant', track_source: 'TrackSource.ValueType', loop: 'Optional[asyncio.AbstractEventLoop]' = None, capacity: 'int' = 0, sample_rate: 'int' = 48000, num_channels: 'int' = 1, frame_size_ms: 'int | None' = None, noise_cancellation: 'Optional[NoiseCancellationOptions | FrameProcessor[AudioFrame]]' = None) -> 'AudioStream'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `participant` | `Participant` | `—` | kw |
| `track_source` | `TrackSource.ValueType` | `—` | kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | kw |
| `capacity` | `int` | `0` | kw |
| `sample_rate` | `int` | `48000` | kw |
| `num_channels` | `int` | `1` | kw |
| `frame_size_ms` | `int \| None` | `None` | kw |
| `noise_cancellation` | `Optional[NoiseCancellationOptions \| FrameProcessor[AudioFrame]]` | `None` | kw |

**Returns:** `AudioStream`

### `from_track`

Create an `AudioStream` from an existing audio track.

Args:
    track (Track): The audio track from which to receive audio.
    loop (Optional[asyncio.AbstractEventLoop], optional): The event loop t…

```python
livekit.rtc.AudioStream.from_track(*, track: 'Track', loop: 'Optional[asyncio.AbstractEventLoop]' = None, capacity: 'int' = 0, sample_rate: 'int' = 48000, num_channels: 'int' = 1, frame_size_ms: 'int | None' = None, noise_cancellation: 'Optional[NoiseCancellationOptions | FrameProcessor[AudioFrame]]' = None) -> 'AudioStream'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `track` | `Track` | `—` | kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | kw |
| `capacity` | `int` | `0` | kw |
| `sample_rate` | `int` | `48000` | kw |
| `num_channels` | `int` | `1` | kw |
| `frame_size_ms` | `int \| None` | `None` | kw |
| `noise_cancellation` | `Optional[NoiseCancellationOptions \| FrameProcessor[AudioFrame]]` | `None` | kw |

**Returns:** `AudioStream`

### `livekit.rtc.ByteStreamWriter` methods

### `aclose`

```python
livekit.rtc.ByteStreamWriter.aclose(self, *, reason: 'str' = '', attributes: 'Optional[Dict[str, str]]' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reason` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |

### `write`

```python
livekit.rtc.ByteStreamWriter.write(self, data: 'bytes')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `bytes` | `—` | pos/kw |

### `livekit.rtc.DataTrackStream` methods

### `aclose`

```python
livekit.rtc.DataTrackStream.aclose(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Explicitly close the subscription and unsubscribe.

```python
livekit.rtc.DataTrackStream.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `read`

Read a single frame, or ``None`` if the stream has ended.

```python
livekit.rtc.DataTrackStream.read(self) -> 'Optional[DataTrackFrame]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Optional[DataTrackFrame]`

### `livekit.rtc.E2EEManager` methods

### `frame_cryptors`

Retrieves the list of frame cryptors for participants.

Returns:
    List[FrameCryptor]: A list of FrameCryptor instances.

Example:
    ```python
    cryptors = e2ee_manager.frame_cryptors()
    for…

```python
livekit.rtc.E2EEManager.frame_cryptors(self) -> List[livekit.rtc.e2ee.FrameCryptor]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[livekit.rtc.e2ee.FrameCryptor]`

### `set_enabled`

Enables or disables end-to-end encryption.

Parameters:
    enabled (bool): True to enable, False to disable.

Example:
    ```python
    e2ee_manager.set_enabled(True)
    ```

```python
livekit.rtc.E2EEManager.set_enabled(self, enabled: bool) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `enabled` | `bool` | `—` | pos/kw |

### `livekit.rtc.EventEmitter` methods

### `emit`

Trigger all callbacks associated with the given event.

Args:
    event (T): The event to emit.
    *args: Positional arguments to pass to the callbacks.

Example:
    Basic usage of emit:

    ```py…

```python
livekit.rtc.EventEmitter.emit(self, event: -T_contra, *args) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `off`

Unregister a callback from an event.

Args:
    event (T): The event to stop listening to.
    callback (Callable): The callback to remove.

Example:
    Removing a callback:

    ```python
    emitt…

```python
livekit.rtc.EventEmitter.off(self, event: -T_contra, callback: Callable) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `callback` | `Callable` | `—` | pos/kw |

### `on`

Register a callback to be called whenever the event is emitted.

If a callback is provided, it registers the callback directly.
If no callback is provided, it returns a decorator for use with functio…

```python
livekit.rtc.EventEmitter.on(self, event: -T_contra, callback: Optional[Callable] = None) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `callback` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Callable`

### `once`

Register a callback to be called only once when the event is emitted.

If a callback is provided, it registers the callback directly.
If no callback is provided, it returns a decorator for use with f…

```python
livekit.rtc.EventEmitter.once(self, event: -T_contra, callback: Optional[Callable] = None) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `callback` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Callable`

### `livekit.rtc.FrameCryptor` methods

### `set_enabled`

Enables or disables frame encryption.

Parameters:
    enabled (bool): True to enable, False to disable.

Example:
    ```python
    frame_cryptor.set_enabled(True)
    ```

```python
livekit.rtc.FrameCryptor.set_enabled(self, enabled: bool) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `enabled` | `bool` | `—` | pos/kw |

### `set_key_index`

Sets the key index for encryption/decryption.

Parameters:
    key_index (int): The new key index.

Example:
    ```python
    frame_cryptor.set_key_index(3)
    ```

```python
livekit.rtc.FrameCryptor.set_key_index(self, key_index: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

### `livekit.rtc.KeyProvider` methods

### `export_key`

Exports the encryption key for a specific participant.

Parameters:
    participant_identity (str): The identity of the participant.
    key_index (int): The index of the key to export.

Returns:…

```python
livekit.rtc.KeyProvider.export_key(self, participant_identity: str, key_index: int) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `participant_identity` | `str` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `export_shared_key`

Exports the shared encryption key.

Parameters:
    key_index (int): The index of the key to export.

Returns:
    bytes: The exported shared key.

Example:
    ```python
    key = key_provider.expor…

```python
livekit.rtc.KeyProvider.export_shared_key(self, key_index: int) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `ratchet_key`

Ratchets the encryption key for a specific participant to a new key.

Parameters:
    participant_identity (str): The identity of the participant.
    key_index (int): The index of the key to ratchet…

```python
livekit.rtc.KeyProvider.ratchet_key(self, participant_identity: str, key_index: int) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `participant_identity` | `str` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `ratchet_shared_key`

Ratchets the shared encryption key to a new key.

Parameters:
    key_index (int): The index of the key to ratchet.

Returns:
    bytes: The new ratcheted shared key.

Example:
    ```python
    new_…

```python
livekit.rtc.KeyProvider.ratchet_shared_key(self, key_index: int) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `set_key`

Sets the encryption key for a specific participant.

Parameters:
    participant_identity (str): The identity of the participant.
    key (bytes): The encryption key to set.
    key_index (int): The…

```python
livekit.rtc.KeyProvider.set_key(self, participant_identity: str, key: bytes, key_index: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `participant_identity` | `str` | `—` | pos/kw |
| `key` | `bytes` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

### `set_shared_key`

Sets the shared encryption key.

Parameters:
    key (bytes): The new shared key.
    key_index (int): The index of the key.

Example:
    ```python
    key_provider.set_shared_key(b"my_shared_key",…

```python
livekit.rtc.KeyProvider.set_shared_key(self, key: bytes, key_index: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `bytes` | `—` | pos/kw |
| `key_index` | `int` | `—` | pos/kw |

### `livekit.rtc.LocalAudioTrack` methods

### `create_audio_track`

```python
livekit.rtc.LocalAudioTrack.create_audio_track(name: str, source: 'AudioSource') -> 'LocalAudioTrack'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `source` | `AudioSource` | `—` | pos/kw |

**Returns:** `LocalAudioTrack`

### `get_stats`

```python
livekit.rtc.LocalAudioTrack.get_stats(self) -> List[stats_pb2.RtcStats]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[stats_pb2.RtcStats]`

### `mute`

```python
livekit.rtc.LocalAudioTrack.mute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unmute`

```python
livekit.rtc.LocalAudioTrack.unmute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.LocalDataTrack` methods

### `is_published`

Whether or not the track is still published.

```python
livekit.rtc.LocalDataTrack.is_published(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `try_push`

Try pushing a frame to subscribers of the track.

See :class:`DataTrackFrame` for how to construct a frame and attach metadata.

Args:
    frame: The data track frame to send.

Raises:
    PushFrameE…

```python
livekit.rtc.LocalDataTrack.try_push(self, frame: 'DataTrackFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `frame` | `DataTrackFrame` | `—` | pos/kw |

### `unpublish`

Unpublishes the track.

```python
livekit.rtc.LocalDataTrack.unpublish(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.LocalParticipant` methods

### `perform_rpc`

Initiate an RPC call to a remote participant.

Args:
    destination_identity (str): The `identity` of the destination participant
    method (str): The method name to call
    payload (str): The met…

```python
livekit.rtc.LocalParticipant.perform_rpc(self, *, destination_identity: 'str', method: 'str', payload: 'str', response_timeout: 'Optional[float]' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `destination_identity` | `str` | `—` | kw |
| `method` | `str` | `—` | kw |
| `payload` | `str` | `—` | kw |
| `response_timeout` | `Optional[float]` | `None` | kw |

**Returns:** `str`

### `publish_data`

Publish arbitrary data to the room.

Args:
    payload (Union[bytes, str]): The data to publish.
    reliable (bool, optional): Whether to send reliably or not. Defaults to True.
    destination_iden…

```python
livekit.rtc.LocalParticipant.publish_data(self, payload: 'Union[bytes, str]', *, reliable: 'bool' = True, destination_identities: 'List[str]' = [], topic: 'str' = '') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `payload` | `Union[bytes, str]` | `—` | pos/kw |
| `reliable` | `bool` | `True` | kw |
| `destination_identities` | `List[str]` | `[]` | kw |
| `topic` | `str` | `''` | kw |

### `publish_data_track`

Publishes a data track.

Args:
    name: The track name used to identify the track to other participants.
        Must not be empty and must be unique per publisher.

Returns:
    The published data…

```python
livekit.rtc.LocalParticipant.publish_data_track(self, *, name: 'str') -> 'LocalDataTrack'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | kw |

**Returns:** `LocalDataTrack`

### `publish_dtmf`

Publish SIP DTMF message.

Args:
    code (int): DTMF code.
    digit (str): DTMF digit.

Raises:
    PublishDTMFError: If there is an error in publishing SIP DTMF message.

```python
livekit.rtc.LocalParticipant.publish_dtmf(self, *, code: 'int', digit: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `code` | `int` | `—` | kw |
| `digit` | `str` | `—` | kw |

### `publish_track`

Publish a local track to the room.

Args:
    track (LocalTrack): The track to publish.
    options (TrackPublishOptions, optional): Options for publishing the track.

Returns:
    LocalTrackPublicat…

```python
livekit.rtc.LocalParticipant.publish_track(self, track: 'LocalTrack', options: 'TrackPublishOptions' = ) -> 'LocalTrackPublication'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `track` | `LocalTrack` | `—` | pos/kw |
| `options` | `TrackPublishOptions` | `` | pos/kw |

**Returns:** `LocalTrackPublication`

### `publish_transcription`

Publish transcription data to the room.

Args:
    transcription (Transcription): The transcription data to publish.

Raises:
    PublishTranscriptionError: If there is an error in publishing transcr…

```python
livekit.rtc.LocalParticipant.publish_transcription(self, transcription: 'Transcription') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `transcription` | `Transcription` | `—` | pos/kw |

### `register_rpc_method`

Establishes the participant as a receiver for calls of the specified RPC method.
Can be used either as a decorator or a regular method.

The handler will receive one argument of type `RpcInvocationDa…

```python
livekit.rtc.LocalParticipant.register_rpc_method(self, method_name: 'str', handler: 'Optional[F]' = None) -> 'Union[F, Callable[[F], F]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `method_name` | `str` | `—` | pos/kw |
| `handler` | `Optional[F]` | `None` | pos/kw |

**Returns:** `Union[F, Callable[[F], F]]`

### `send_file`

```python
livekit.rtc.LocalParticipant.send_file(self, file_path: 'str', *, topic: 'str' = '', destination_identities: 'Optional[List[str]]' = None, attributes: 'Optional[Dict[str, str]]' = None, stream_id: 'str | None' = None) -> 'ByteStreamInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_path` | `str` | `—` | pos/kw |
| `topic` | `str` | `''` | kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |
| `stream_id` | `str \| None` | `None` | kw |

**Returns:** `ByteStreamInfo`

### `send_text`

```python
livekit.rtc.LocalParticipant.send_text(self, text: 'str', *, destination_identities: 'Optional[List[str]]' = None, topic: 'str' = '', attributes: 'Optional[Dict[str, str]]' = None, reply_to_id: 'str | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |
| `topic` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |
| `reply_to_id` | `str \| None` | `None` | kw |

### `set_attributes`

Set custom attributes for the local participant.

Note: this requires `canUpdateOwnMetadata` permission.

Args:
    attributes (dict[str, str]): A dictionary of attributes to set.

```python
livekit.rtc.LocalParticipant.set_attributes(self, attributes: 'dict[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attributes` | `dict[str, str]` | `—` | pos/kw |

### `set_metadata`

Set the metadata for the local participant.

Note: this requires `canUpdateOwnMetadata` permission.

Args:
    metadata (str): The new metadata.

```python
livekit.rtc.LocalParticipant.set_metadata(self, metadata: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `metadata` | `str` | `—` | pos/kw |

### `set_name`

Set the name for the local participant.

Note: this requires `canUpdateOwnMetadata` permission.

Args:
    name (str): The new name.

```python
livekit.rtc.LocalParticipant.set_name(self, name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `set_track_subscription_permissions`

Set the track subscription permissions for the local participant.

Args:
    allow_all_participants (bool): Whether to allow all participants to subscribe to this participant's tracks.
    participan…

```python
livekit.rtc.LocalParticipant.set_track_subscription_permissions(self, *, allow_all_participants: 'bool', participant_permissions: 'Optional[List[ParticipantTrackPermission]]' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `allow_all_participants` | `bool` | `—` | kw |
| `participant_permissions` | `Optional[List[ParticipantTrackPermission]]` | `None` | kw |

### `stream_bytes`

Returns a ByteStreamWriter that allows to write individual chunks of bytes to a byte stream.
In cases where you want to simply send a file from the file system use send_file() instead.

```python
livekit.rtc.LocalParticipant.stream_bytes(self, name: 'str', *, total_size: 'int | None' = None, mime_type: 'str' = 'application/octet-stream', attributes: 'Optional[Dict[str, str]]' = None, stream_id: 'str | None' = None, destination_identities: 'Optional[List[str]]' = None, topic: 'str' = '') -> 'ByteStreamWriter'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `total_size` | `int \| None` | `None` | kw |
| `mime_type` | `str` | `'application/octet-stream'` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |
| `stream_id` | `str \| None` | `None` | kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |
| `topic` | `str` | `''` | kw |

**Returns:** `ByteStreamWriter`

### `stream_text`

Returns a TextStreamWriter that allows to write individual chunks of text to a text stream.
In most cases where you want to simply send a text message use send_text() instead.

```python
livekit.rtc.LocalParticipant.stream_text(self, *, destination_identities: 'Optional[List[str]]' = None, topic: 'str' = '', attributes: 'Optional[Dict[str, str]]' = None, stream_id: 'str | None' = None, reply_to_id: 'str | None' = None, total_size: 'int | None' = None, sender_identity: 'str | None' = None) -> 'TextStreamWriter'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `destination_identities` | `Optional[List[str]]` | `None` | kw |
| `topic` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |
| `stream_id` | `str \| None` | `None` | kw |
| `reply_to_id` | `str \| None` | `None` | kw |
| `total_size` | `int \| None` | `None` | kw |
| `sender_identity` | `str \| None` | `None` | kw |

**Returns:** `TextStreamWriter`

### `unpublish_track`

Unpublish a track from the room.

Args:
    track_sid (str): The SID of the track to unpublish.

Raises:
    UnpublishTrackError: If there is an error in unpublishing the track.

```python
livekit.rtc.LocalParticipant.unpublish_track(self, track_sid: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `track_sid` | `str` | `—` | pos/kw |

### `unregister_rpc_method`

Unregisters a previously registered RPC method.

Args:
    method (str): The name of the RPC method to unregister

```python
livekit.rtc.LocalParticipant.unregister_rpc_method(self, method: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `method` | `str` | `—` | pos/kw |

### `livekit.rtc.LocalTrackPublication` methods

### `wait_for_subscription`

```python
livekit.rtc.LocalTrackPublication.wait_for_subscription(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.LocalVideoTrack` methods

### `create_video_track`

```python
livekit.rtc.LocalVideoTrack.create_video_track(name: str, source: 'VideoSource') -> 'LocalVideoTrack'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `source` | `VideoSource` | `—` | pos/kw |

**Returns:** `LocalVideoTrack`

### `get_stats`

```python
livekit.rtc.LocalVideoTrack.get_stats(self) -> List[stats_pb2.RtcStats]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[stats_pb2.RtcStats]`

### `mute`

```python
livekit.rtc.LocalVideoTrack.mute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unmute`

```python
livekit.rtc.LocalVideoTrack.unmute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.MediaDevices` methods

### `default_input_device`

Return the default input device index (or None).

```python
livekit.rtc.MediaDevices.default_input_device(self) -> 'Optional[int]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Optional[int]`

### `default_output_device`

Return the default output device index (or None).

```python
livekit.rtc.MediaDevices.default_output_device(self) -> 'Optional[int]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Optional[int]`

### `list_input_devices`

List available input devices.

Returns a list of dictionaries with the `sounddevice` metadata and an
added `index` key corresponding to the device index.

```python
livekit.rtc.MediaDevices.list_input_devices(self) -> 'list[dict[str, Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[dict[str, Any]]`

### `list_output_devices`

List available output devices with indices.

```python
livekit.rtc.MediaDevices.list_output_devices(self) -> 'list[dict[str, Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[dict[str, Any]]`

### `open_input`

Open the default (or chosen) audio input device and start capture.

Frames are sliced into 10 ms chunks. If any processing option is enabled,
an `AudioProcessingModule` is created and applied to each…

```python
livekit.rtc.MediaDevices.open_input(self, *, enable_aec: 'bool' = True, noise_suppression: 'bool' = True, high_pass_filter: 'bool' = True, auto_gain_control: 'bool' = True, input_device: 'Optional[int]' = None, queue_capacity: 'int' = 50, input_channel_index: 'Optional[int]' = None) -> 'InputCapture'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `enable_aec` | `bool` | `True` | kw |
| `noise_suppression` | `bool` | `True` | kw |
| `high_pass_filter` | `bool` | `True` | kw |
| `auto_gain_control` | `bool` | `True` | kw |
| `input_device` | `Optional[int]` | `None` | kw |
| `queue_capacity` | `int` | `50` | kw |
| `input_channel_index` | `Optional[int]` | `None` | kw |

**Returns:** `InputCapture`

### `open_output`

Create an `OutputPlayer` for rendering and (optionally) AEC reverse.

If an input device was opened with AEC enabled, the output player will
automatically feed the APM's reverse stream for echo cance…

```python
livekit.rtc.MediaDevices.open_output(self, *, output_device: 'Optional[int]' = None) -> 'OutputPlayer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `output_device` | `Optional[int]` | `None` | kw |

**Returns:** `OutputPlayer`

### `livekit.rtc.RemoteAudioTrack` methods

### `get_stats`

```python
livekit.rtc.RemoteAudioTrack.get_stats(self) -> List[stats_pb2.RtcStats]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[stats_pb2.RtcStats]`

### `livekit.rtc.RemoteDataTrack` methods

### `is_published`

Whether or not the track is still published.

```python
livekit.rtc.RemoteDataTrack.is_published(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `subscribe`

Subscribes to the data track to receive frames.

Args:
    buffer_size: Maximum number of received frames to buffer internally.
        When ``None``, the default buffer size is used.
        Zero is…

```python
livekit.rtc.RemoteDataTrack.subscribe(self, *, buffer_size: 'Optional[int]' = None) -> 'DataTrackStream'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `buffer_size` | `Optional[int]` | `None` | kw |

**Returns:** `DataTrackStream`

### `livekit.rtc.RemoteTrackPublication` methods

### `set_subscribed`

```python
livekit.rtc.RemoteTrackPublication.set_subscribed(self, subscribed: bool)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `subscribed` | `bool` | `—` | pos/kw |

### `livekit.rtc.RemoteVideoTrack` methods

### `get_stats`

```python
livekit.rtc.RemoteVideoTrack.get_stats(self) -> List[stats_pb2.RtcStats]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[stats_pb2.RtcStats]`

### `livekit.rtc.Room` methods

### `connect`

Connects to a LiveKit room using the specified URL and token.

Parameters:
    url (str): The WebSocket URL of the LiveKit server to connect to.
    token (str): The access token for authentication a…

```python
livekit.rtc.Room.connect(self, url: 'str', token: 'str', options: 'RoomOptions' = RoomOptions(auto_subscribe=True, dynacast=False, e2ee=None, encryption=None, rtc_config=None, connect_timeout=None, single_peer_connection=None)) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `str` | `—` | pos/kw |
| `token` | `str` | `—` | pos/kw |
| `options` | `RoomOptions` | `RoomOptions(auto_subscribe=True, dynacast=False, e2ee=None, encryption=None, rtc_config=None, connect_timeout=None, single_peer_connection=None)` | pos/kw |

### `disconnect`

Disconnects from the room.

```python
livekit.rtc.Room.disconnect(self, *, reason: 'DisconnectReason.ValueType' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reason` | `DisconnectReason.ValueType` | `1` | kw |

### `emit`

Trigger all callbacks associated with the given event.

Args:
    event (T): The event to emit.
    *args: Positional arguments to pass to the callbacks.

Example:
    Basic usage of emit:

    ```py…

```python
livekit.rtc.Room.emit(self, event: -T_contra, *args) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `get_rtc_stats`

```python
livekit.rtc.Room.get_rtc_stats(self) -> 'RtcStats'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `RtcStats`

### `isconnected`

Checks if the room is currently connected.

Returns:
    bool: True if connected, False otherwise.

```python
livekit.rtc.Room.isconnected(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `off`

Unregister a callback from an event.

Args:
    event (T): The event to stop listening to.
    callback (Callable): The callback to remove.

Example:
    Removing a callback:

    ```python
    emitt…

```python
livekit.rtc.Room.off(self, event: -T_contra, callback: Callable) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `callback` | `Callable` | `—` | pos/kw |

### `on`

Registers an event handler for a specific event type.

Parameters:
    event (EventTypes): The name of the event to listen for.
    callback (Callable): The function to call when the event occurs.

R…

```python
livekit.rtc.Room.on(self, event: 'EventTypes', callback: 'Optional[Callable]' = None) -> 'Callable'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `EventTypes` | `—` | pos/kw |
| `callback` | `Optional[Callable]` | `None` | pos/kw |

**Returns:** `Callable`

### `once`

Register a callback to be called only once when the event is emitted.

If a callback is provided, it registers the callback directly.
If no callback is provided, it returns a decorator for use with f…

```python
livekit.rtc.Room.once(self, event: -T_contra, callback: Optional[Callable] = None) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `T_contra` | `—` | pos/kw |
| `callback` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Callable`

### `register_byte_stream_handler`

```python
livekit.rtc.Room.register_byte_stream_handler(self, topic: 'str', handler: 'ByteStreamHandler')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |
| `handler` | `ByteStreamHandler` | `—` | pos/kw |

### `register_text_stream_handler`

```python
livekit.rtc.Room.register_text_stream_handler(self, topic: 'str', handler: 'TextStreamHandler')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |
| `handler` | `TextStreamHandler` | `—` | pos/kw |

### `unregister_byte_stream_handler`

```python
livekit.rtc.Room.unregister_byte_stream_handler(self, topic: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |

### `unregister_text_stream_handler`

```python
livekit.rtc.Room.unregister_text_stream_handler(self, topic: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `topic` | `str` | `—` | pos/kw |

### `livekit.rtc.TextStreamReader` methods

### `read_all`

```python
livekit.rtc.TextStreamReader.read_all(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `livekit.rtc.TextStreamWriter` methods

### `aclose`

```python
livekit.rtc.TextStreamWriter.aclose(self, *, reason: 'str' = '', attributes: 'Optional[Dict[str, str]]' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reason` | `str` | `''` | kw |
| `attributes` | `Optional[Dict[str, str]]` | `None` | kw |

### `write`

```python
livekit.rtc.TextStreamWriter.write(self, text: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

### `livekit.rtc.Track` methods

### `get_stats`

```python
livekit.rtc.Track.get_stats(self) -> List[stats_pb2.RtcStats]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[stats_pb2.RtcStats]`

### `livekit.rtc.VideoFrame` methods

### `convert`

Converts the current video frame to a different format type, optionally flipping
the frame vertically.

Args:
    type (proto_video.VideoBufferType.ValueType): The target format type to convert to…

```python
livekit.rtc.VideoFrame.convert(self, type: int, *, flip_y: bool = False) -> 'VideoFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `type` | `int` | `—` | pos/kw |
| `flip_y` | `bool` | `False` | kw |

**Returns:** `VideoFrame`

### `get_plane`

Returns the memoryview of a specific plane in the video frame, based on its index.

Some video formats (e.g., I420, NV12) contain multiple planes (Y, U, V channels).
This method allows access to indi…

```python
livekit.rtc.VideoFrame.get_plane(self, plane_nth: int) -> Optional[memoryview]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `plane_nth` | `int` | `—` | pos/kw |

**Returns:** `typing.Optional[memoryview]`

### `livekit.rtc.VideoSource` methods

### `aclose`

```python
livekit.rtc.VideoSource.aclose(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `capture_frame`

```python
livekit.rtc.VideoSource.capture_frame(self, frame: 'VideoFrame', *, timestamp_us: 'int' = 0, rotation: 'proto_video.VideoRotation.ValueType' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `frame` | `VideoFrame` | `—` | pos/kw |
| `timestamp_us` | `int` | `0` | kw |
| `rotation` | `proto_video.VideoRotation.ValueType` | `0` | kw |

### `livekit.rtc.VideoStream` methods

### `aclose`

```python
livekit.rtc.VideoStream.aclose(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_participant`

```python
livekit.rtc.VideoStream.from_participant(*, participant: 'Participant', track_source: 'TrackSource.ValueType', loop: 'Optional[asyncio.AbstractEventLoop]' = None, format: 'Optional[proto_video_frame.VideoBufferType.ValueType]' = None, capacity: 'int' = 0) -> 'VideoStream'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `participant` | `Participant` | `—` | kw |
| `track_source` | `TrackSource.ValueType` | `—` | kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | kw |
| `format` | `Optional[proto_video_frame.VideoBufferType.ValueType]` | `None` | kw |
| `capacity` | `int` | `0` | kw |

**Returns:** `VideoStream`

### `from_track`

```python
livekit.rtc.VideoStream.from_track(*, track: 'Track', loop: 'Optional[asyncio.AbstractEventLoop]' = None, format: 'Optional[proto_video_frame.VideoBufferType.ValueType]' = None, capacity: 'int' = 0) -> 'VideoStream'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `track` | `Track` | `—` | kw |
| `loop` | `Optional[asyncio.AbstractEventLoop]` | `None` | kw |
| `format` | `Optional[proto_video_frame.VideoBufferType.ValueType]` | `None` | kw |
| `capacity` | `int` | `0` | kw |

**Returns:** `VideoStream`

### `livekit.rtc.apm.AudioFrame` methods

### `create`

Create a new empty AudioFrame instance with specified sample rate, number of channels,
and samples per channel.

Args:
    sample_rate (int): The sample rate of the audio in Hz.
    num_channels (int…

```python
livekit.rtc.apm.AudioFrame.create(sample_rate: int, num_channels: int, samples_per_channel: int) -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `to_wav_bytes`

Convert the audio frame data to a WAV-formatted byte stream.

Returns:
    bytes: The audio data encoded in WAV format.

```python
livekit.rtc.apm.AudioFrame.to_wav_bytes(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `livekit.rtc.apm.AudioProcessingModule` methods

### `process_reverse_stream`

Process the reverse audio frame (typically used for echo cancellation in a full-duplex setup).

In an echo cancellation scenario, this method is used to process the "far-end" audio
prior to mixing or…

```python
livekit.rtc.apm.AudioProcessingModule.process_reverse_stream(self, data: 'AudioFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `AudioFrame` | `—` | pos/kw |

### `process_stream`

Process the provided audio frame using the configured audio processing features.

The input audio frame is modified in-place (if applicable) by the underlying audio
processing module (e.g., echo canc…

```python
livekit.rtc.apm.AudioProcessingModule.process_stream(self, data: 'AudioFrame') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `AudioFrame` | `—` | pos/kw |

### `set_stream_delay_ms`

This must be called if and only if echo processing is enabled.

Sets the `delay` in ms between `process_reverse_stream()` receiving a far-end
frame and `process_stream()` receiving a near-end frame c…

```python
livekit.rtc.apm.AudioProcessingModule.set_stream_delay_ms(self, delay_ms: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `delay_ms` | `int` | `—` | pos/kw |

### `livekit.rtc.apm.FfiClient` methods

### `request`

```python
livekit.rtc.apm.FfiClient.request(self, req: ffi_pb2.FfiRequest) -> ffi_pb2.FfiResponse
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `FfiRequest` | `—` | pos/kw |

**Returns:** `<class 'ffi_pb2.FfiResponse'>`

### `livekit.rtc.apm.FfiHandle` methods

### `dispose`

```python
livekit.rtc.apm.FfiHandle.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.audio_filter.FfiClient` methods

### `request`

```python
livekit.rtc.audio_filter.FfiClient.request(self, req: ffi_pb2.FfiRequest) -> ffi_pb2.FfiResponse
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `FfiRequest` | `—` | pos/kw |

**Returns:** `<class 'ffi_pb2.FfiResponse'>`

### `livekit.rtc.audio_frame.AudioFrame` methods

### `create`

Create a new empty AudioFrame instance with specified sample rate, number of channels,
and samples per channel.

Args:
    sample_rate (int): The sample rate of the audio in Hz.
    num_channels (int…

```python
livekit.rtc.audio_frame.AudioFrame.create(sample_rate: int, num_channels: int, samples_per_channel: int) -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `to_wav_bytes`

Convert the audio frame data to a WAV-formatted byte stream.

Returns:
    bytes: The audio data encoded in WAV format.

```python
livekit.rtc.audio_frame.AudioFrame.to_wav_bytes(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `livekit.rtc.audio_frame.FfiHandle` methods

### `dispose`

```python
livekit.rtc.audio_frame.FfiHandle.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `livekit.rtc.audio_mixer.AudioFrame` methods

### `create`

Create a new empty AudioFrame instance with specified sample rate, number of channels,
and samples per channel.

Args:
    sample_rate (int): The sample rate of the audio in Hz.
    num_channels (int…

```python
livekit.rtc.audio_mixer.AudioFrame.create(sample_rate: int, num_channels: int, samples_per_channel: int) -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `to_wav_bytes`

Convert the audio frame data to a WAV-formatted byte stream.

Returns:
    bytes: The audio data encoded in WAV format.

```python
livekit.rtc.audio_mixer.AudioFrame.to_wav_bytes(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `livekit.rtc.audio_mixer.AudioMixer` methods

### `aclose`

Immediately stop mixing and close the mixer.

This cancels the mixing task, and any unconsumed output in the queue may be dropped.

```python
livekit.rtc.audio_mixer.AudioMixer.aclose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `add_stream`

Add an audio stream to the mixer.

The stream is added to the internal set of streams and an empty buffer is initialized for it,
if not already present.

Args:
    stream (AsyncIterator[AudioFrame]):…

```python
livekit.rtc.audio_mixer.AudioMixer.add_stream(self, stream: AsyncIterator[livekit.rtc.audio_frame.AudioFrame]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `AsyncIterator` | `—` | pos/kw |

### `end_input`

Signal that no more streams will be added.

This method marks the mixer as closed so that it flushes any remaining buffered output before ending.
Note that existing streams will still be processed un…

```python
livekit.rtc.audio_mixer.AudioMixer.end_input(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `remove_stream`

Remove an audio stream from the mixer.

This method removes the specified stream and its associated buffer from the mixer.

Args:
    stream (AsyncIterator[AudioFrame]): The audio stream to remove.

```python
livekit.rtc.audio_mixer.AudioMixer.remove_stream(self, stream: AsyncIterator[livekit.rtc.audio_frame.AudioFrame]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `AsyncIterator` | `—` | pos/kw |

### `livekit.rtc.audio_resampler.AudioFrame` methods

### `create`

Create a new empty AudioFrame instance with specified sample rate, number of channels,
and samples per channel.

Args:
    sample_rate (int): The sample rate of the audio in Hz.
    num_channels (int…

```python
livekit.rtc.audio_resampler.AudioFrame.create(sample_rate: int, num_channels: int, samples_per_channel: int) -> 'AudioFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sample_rate` | `int` | `—` | pos/kw |
| `num_channels` | `int` | `—` | pos/kw |
| `samples_per_channel` | `int` | `—` | pos/kw |

**Returns:** `AudioFrame`

### `to_wav_bytes`

Convert the audio frame data to a WAV-formatted byte stream.

Returns:
    bytes: The audio data encoded in WAV format.

```python
livekit.rtc.audio_resampler.AudioFrame.to_wav_bytes(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `livekit.rtc.audio_resampler.AudioResampler` methods

### `flush`

Flush any remaining audio data through the resampler and retrieve the resampled data.

This method should be called when no more input data will be provided to ensure that all internal
buffers are pr…

```python
livekit.rtc.audio_resampler.AudioResampler.flush(self) -> 'list[AudioFrame]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[AudioFrame]`

### `push`

Push audio data into the resampler and retrieve any available resampled data.

This method accepts audio data, resamples it according to the configured input and output rates,
and returns any resampl…

```python
livekit.rtc.audio_resampler.AudioResampler.push(self, data: 'bytearray | AudioFrame') -> 'list[AudioFrame]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `bytearray \| AudioFrame` | `—` | pos/kw |

**Returns:** `list[AudioFrame]`

